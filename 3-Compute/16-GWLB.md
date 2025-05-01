# **Gateway Load Balancer de AWS: Balanceo de Carga para Aplicaciones Virtuales de Seguridad**

## **Introducción al Gateway Load Balancer (GWLB)**
El Gateway Load Balancer de AWS es un servicio administrado que simplifica el despliegue y gestión de **aplicaciones virtuales de red y seguridad** (como firewalls, IDS/IPS) en la nube. Opera en la **capa 3 (red) del modelo OSI** y utiliza el protocolo GENEVE (puerto 6081) para distribuir tráfico a instancias de appliances virtuales.

### **Diagrama de Arquitectura**
```
┌─────────────────────────────────────────────────────────────────┐
│                      Internet Gateway                           │
└───────────────────────────────┬─────────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────────┐
│                   Gateway Load Balancer (GWLB)                  │
│  (Distribuye tráfico a appliances virtuales en un target group) │
└───────────────────────────────┬─────────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────────┐
│                Appliances Virtuales (Target Group)               │
│  (Firewalls, IDS/IPS, DPI) → Inspeccionan tráfico                │
└───────────────────────────────┬─────────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────────┐
│                     Aplicaciones Backend                        │
└─────────────────────────────────────────────────────────────────┘
```

---

## **Características Clave**
### **Tabla Comparativa**
| **Característica**               | **Beneficio**                                                                 |
|----------------------------------|-------------------------------------------------------------------------------|
| **Escalado Automático**          | Integración con Auto Scaling Groups para ajustar capacidad según demanda.     |
| **Alta Disponibilidad**          | Ruteo inteligente hacia appliances saludables (health checks configurables).  |
| **Conexión Privada**             | Usa VPC Endpoints (PrivateLink) para tráfico seguro dentro de la red AWS.     |
| **Integración con Marketplace**  | Despliegue rápido de appliances preconfigurados desde AWS Marketplace.        |
| **Costo-efectivo**               | Pago solo por recursos usados (sin costos iniciales).                         |

---

## **Cómo Funciona el GWLB: Flujo de Tráfico**
1. **Entrada de Tráfico**:
   - El tráfico ingresa por el Internet Gateway.
   - Las tablas de ruta dirigen el tráfico al **GWLB Endpoint**.

2. **Distribución y Inspección**:
   - El GWLB envía el tráfico a los appliances virtuales (firewalls, IDS, etc.).
   - Los appliances inspeccionan el tráfico:
     - **Tráfico válido**: Se reenvía a las aplicaciones backend.
     - **Tráfico malicioso**: Se descarta.

3. **Salida de Tráfico**:
   - El tráfico de retorno pasa nuevamente por los appliances para inspección.
   - Finalmente, sale a Internet a través del Internet Gateway.

---

## **Laboratorio Práctico: Configuración Básica**
### **Paso a Paso con Free Tier**
1. **Prerrequisitos**:
   - 2 subnets en distintas AZs (1 para GWLB, 1 para aplicaciones).
   - Instancias EC2 ejecutando appliances virtuales (ej: firewall de AWS Marketplace).

2. **Crear GWLB**:
   ```mermaid
   graph LR
       A[Consola AWS] --> B[Servicios → EC2 → Load Balancers]
       B --> C[Crear Gateway Load Balancer]
       C --> D[Definir listeners - puerto 6081]
       D --> E[Asociar target group con appliances]
   ```

3. **Configurar Rutas**:
   - Modificar tablas de ruta del VPC para dirigir tráfico al GWLB.

4. **Verificación**:
   - Monitorear tráfico inspeccionado con CloudWatch Logs.

---

## **Casos de Uso**
### **Lista de Aplicaciones**
1. **Seguridad Centralizada**:
   - Consolidación de firewalls (NGFW) y sistemas IDS/IPS en arquitecturas multi-VPC.
2. **Cumplimiento Normativo**:
   - Inspección profunda (DPI) para regulaciones como PCI-DSS o HIPAA.
3. **Visibilidad de Red**:
   - Monitoreo con herramientas de analytics (ej: Splunk, Darktrace).
4. **Automatización**:
   - Despliegue automatizado con CloudFormation/Terraform.

---

## **Comparativa con Otros Load Balancers de AWS**
| **Tipo**               | **Capa OSI** | **Uso Principal**                          | **Protocolos**        |
|------------------------|-------------|--------------------------------------------|-----------------------|
| **Application LB**     | Capa 7      | Enrutamiento HTTP/HTTPS                    | HTTP/HTTPS/gRPC       |
| **Network LB**         | Capa 4      | Tráfico de ultra baja latencia             | TCP/UDP/TLS           |
| **Gateway LB**         | Capa 3      | Inspección con appliances virtuales        | GENEVE (6081)         |

---

## **Conclusión**
El Gateway Load Balancer es ideal para:
✔ **Empresas que usan appliances virtuales** de seguridad/red.  
✔ **Arquitecturas híbridas** que requieren inspección profunda de tráfico.  
✔ **Centralizar políticas de seguridad** en entornos multi-VPC.  

📌 **Tip**: Usa **AWS Firewall Manager** con GWLB para gestionar reglas a escala.  

🔗 **Documentación**: [AWS Gateway LB](https://docs.aws.amazon.com/elasticloadbalancing/latest/gateway/introduction.html)  
