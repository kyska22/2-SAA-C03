# **Balanceo de Carga en Nivel 4 (OSI) con Network Load Balancer (NLB) en AWS**

## **Introducción**
En este módulo, exploraremos cómo configurar un **Network Load Balancer (NLB)** en AWS para manejar tráfico **TCP y UDP**, operando en el **nivel 4 del modelo OSI**. A diferencia del *Application Load Balancer (ALB)*, que opera en la capa 7 (HTTP/HTTPS), el NLB enruta el tráfico basado en **protocolo, IP y puerto**.

---

## **Arquitectura Propuesta**
### **Diagrama de la Solución**
```
┌─────────────────────────────────────────────────────────────────┐
│                          Network Load Balancer                   │
│  (Escucha en puertos TCP:6381 y UDP:6380)                        │
└───────────────┬──────────────────────────────────────┬───────────┘
                │                                      │
       ┌───────▼───────┐                     ┌────────▼────────┐
       │  Target Group │                     │  Target Group   │
       │    (TCP)      │                     │     (UDP)       │
       └───────┬───────┘                     └────────┬────────┘
               │                                      │
      ┌────────▼───────┐                   ┌──────────▼──────────┐
      │ EC2 Instancia  │                   │  EC2 Instancia      │
      │ TCP Server 1   │                   │  UDP Server 1       │
      └────────────────┘                   └─────────────────────┘
      ┌────────────────┐                   ┌─────────────────────┐
      │ EC2 Instancia  │                   │  EC2 Instancia      │
      │ TCP Server 2   │                   │  UDP Server 2       │
      └────────────────┘                   └─────────────────────┘
```

---

## **Pasos para Implementar el NLB**
### **1. Configuración Inicial**
- **Exportar la VPC predeterminada**:
  ```bash
  export VPC=$(aws ec2 describe-vpcs --query 'Vpcs[?IsDefault].VpcId' --output text)
  ```
- **Crear un Security Group**:
  ```bash
  aws ec2 create-security-group --group-name "myNLB-SG" --description "Security Group for NLB" --vpc-id $VPC
  export SG=$(aws ec2 describe-security-groups --group-names "myNLB-SG" --query 'SecurityGroups[0].GroupId' --output text)
  ```
- **Reglas de Ingress**:
  ```bash
  aws ec2 authorize-security-group-ingress --group-id $SG --protocol tcp --port 22 --cidr $(curl ifconfig.me)/32
  aws ec2 authorize-security-group-ingress --group-id $SG --protocol udp --port 6380 --cidr 0.0.0.0/0
  aws ec2 authorize-security-group-ingress --group-id $SG --protocol tcp --port 6381 --cidr 0.0.0.0/0
  ```

---

### **2. Creación de Subnets y EC2 Instances**
#### **Tabla de Subnets**
| **Subnet** | **AZ**       | **CIDR Block** |
|------------|--------------|----------------|
| Subnet-1   | us-east-1a   | 192.168.0.0/24 |
| Subnet-2   | us-east-1b   | 192.168.1.0/24 |

#### **Comandos para Crear Subnets**
```bash
aws ec2 create-subnet --vpc-id $VPC --availability-zone us-east-1a --cidr-block 192.168.0.0/24
export SUBNET1=$(aws ec2 describe-subnets --filters "Name=cidr-block,Values=192.168.0.0/24" --query 'Subnets[0].SubnetId' --output text)

aws ec2 create-subnet --vpc-id $VPC --availability-zone us-east-1b --cidr-block 192.168.1.0/24
export SUBNET2=$(aws ec2 describe-subnets --filters "Name=cidr-block,Values=192.168.1.0/24" --query 'Subnets[0].SubnetId' --output text)
```

#### **Instancias EC2**
- **TCP Servers** (User Data: `TCP-Server-1` y `TCP-Server-2`)
- **UDP Servers** (User Data: `UDP-Server-1` y `UDP-Server-2`)

```bash
aws ec2 run-instances --image-id ami-0abcdef1234567890 --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids $SG --subnet-id $SUBNET1 --user-data file://TCP-Server-1.txt --associate-public-ip-address
export TCP1=$(aws ec2 describe-instances --filters "Name=subnet-id,Values=$SUBNET1" --query 'Reservations[0].Instances[0].InstanceId' --output text)
```

---

### **3. Configuración del Network Load Balancer**
#### **Creación del NLB**
```bash
aws elbv2 create-load-balancer --name myNLB --type network --subnets $SUBNET1 $SUBNET2
export NLB_ARN=$(aws elbv2 describe-load-balancers --names myNLB --query 'LoadBalancers[0].LoadBalancerArn' --output text)
```

#### **Target Groups**
| **Target Group** | **Protocol** | **Port** |
|------------------|--------------|----------|
| TCP-TG           | TCP          | 6381     |
| UDP-TG           | UDP          | 6380     |

```bash
aws elbv2 create-target-group --name TCP-TG --protocol TCP --port 6381 --vpc-id $VPC
export TCP_TG_ARN=$(aws elbv2 describe-target-groups --names TCP-TG --query 'TargetGroups[0].TargetGroupArn' --output text)
```

#### **Registro de Targets**
```bash
aws elbv2 register-targets --target-group-arn $TCP_TG_ARN --targets Id=$TCP1 Id=$TCP2
```

#### **Listeners**
```bash
aws elbv2 create-listener --load-balancer-arn $NLB_ARN --protocol TCP --port 6381 --default-actions Type=forward,TargetGroupArn=$TCP_TG_ARN
```

---

### **4. Pruebas de Conectividad**
#### **Enviar una Solicitud TCP**
```bash
nc <NLB-DNS-Name> 6381
```
**Respuesta Esperada**:
```
Return from TCP Server 1: Hi
```

#### **Enviar una Solicitud UDP (Python Script)**
```python
import socket
import sys

UDP_IP = sys.argv[1]
UDP_PORT = 6380
MESSAGE = "Hello UDP Server"

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.sendto(MESSAGE.encode(), (UDP_IP, UDP_PORT))
```

---

### **5. Limpieza de Recursos**
#### **Orden de Eliminación**
1. **Listeners**
2. **Target Groups**
3. **Load Balancer**
4. **EC2 Instances**
5. **Subnets**
6. **Security Group**

```bash
aws elbv2 delete-listener --listener-arn $LISTENER_ARN
aws ec2 terminate-instances --instance-ids $TCP1 $TCP2 $UDP1 $UDP2
```

---

## **Conclusión**
El **Network Load Balancer (NLB)** es ideal para aplicaciones que requieren:
✔ **Alto rendimiento** (millones de solicitudes por segundo)  
✔ **Baja latencia** (nivel 4 del OSI)  
✔ **Soporte para TCP/UDP**  

**Diferencia clave vs ALB**:
| **Feature**       | **NLB** (Layer 4)       | **ALB** (Layer 7)       |
|-------------------|-------------------------|-------------------------|
| Protocolos        | TCP, UDP, TLS           | HTTP, HTTPS, gRPC       |
| Enrutamiento      | IP/Puerto               | Path, Headers, Host     |
| Casos de Uso      | Gaming, IoT, Streaming  | Web Apps, Microservicios|

---

### **Referencias**
- [AWS NLB Documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)
- [Netcat (nc) Command Guide](https://linux.die.net/man/1/nc)  
