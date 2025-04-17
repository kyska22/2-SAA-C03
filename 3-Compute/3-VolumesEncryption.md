# **Cifrado de Volúmenes EBS y Uso de Key Pairs en EC2**

## **Introducción**  
En este módulo final de EC2, cubriremos dos temas críticos para la seguridad y gestión de almacenamiento en AWS:  
1. **Cifrado de volúmenes EBS** (usando AWS KMS).  
2. **Key Pairs para conexiones SSH**.  

Al final, realizaremos un laboratorio práctico para consolidar estos conceptos.  

---

## **1. Volúmenes EBS: Conceptos Clave**  
Los **Amazon EBS (Elastic Block Store)** son dispositivos de almacenamiento de bloques duraderos que se adjuntan a instancias EC2.  

### **Tabla: Características de EBS**  
| **Aspecto**               | **Descripción**                                                                 | **Importante para el Examen AWS**          |
|---------------------------|-------------------------------------------------------------------------------|------------------------------------------|
| **Tipo de Almacenamiento** | **Block-level** (vs. S3 que es object-level).                                | Diferenciar EBS (bloques) vs. S3 (objetos). |
| **Flexibilidad**          | Permite redimensionar, cambiar tipo y ajustar IOPS **sin detener la instancia**. | Soporte para volúmenes en producción.       |
| **Persistencia**         | Los datos persisten incluso si la instancia EC2 se detiene (a menos que se configure lo contrario). | Ideal para bases de datos y sistemas críticos. |
| **Multi-Attach**        | Un volumen EBS puede montarse en **múltiples instancias simultáneamente** (solo ciertos tipos). | Útil para aplicaciones clusterizadas.     |

### **Diagrama: Multi-Attach EBS**  
```plaintext
[Volumen EBS (io1/io2)]
   ├── Instancia EC2 A
   ├── Instancia EC2 B
   └── Instancia EC2 C
```
> 📌 **Requisito:** Todas las instancias y el volumen deben estar en la **misma AZ**.

---

## **2. Cifrado de Volúmenes EBS**  
AWS utiliza **AWS KMS (Key Management Service)** para cifrar volúmenes EBS.  

### **Lista: Datos Cifrados**  
- 🔒 **Data at rest**: Información almacenada en el volumen.  
- 🔒 **Data in transit**: Tráfico entre la instancia EC2 y el volumen EBS.  
- 🔒 **Snapshots**: Copias de seguridad derivadas de volúmenes cifrados.  
- 🔒 **Volúmenes nuevos**: Creados a partir de snapshots cifrados.  

#### **Algoritmo de Cifrado**  
- **AES-256** (estándar industrial).  

### **Proceso de Cifrado**  
1. **Volumen no cifrado** → Se crea un *snapshot*.  
2. **Snapshot** → Se cifra con una **KMS Key**.  
3. **Nuevo volumen** → Se genera a partir del snapshot cifrado.  

```mermaid
graph LR
  A[Volumen EBS Sin Cifrar] --> B(Snapshot)
  B --> C[Snapshot Cifrado - KMS]
  C --> D[Nuevo Volumen EBS Cifrado]
```

---

## **3. Key Pairs para Conexiones SSH**  
Los **Key Pairs** son credenciales de seguridad para autenticarse en instancias EC2 (Linux/Windows).  

### **Lista Ordenada: Flujo de Trabajo**  
1. **Crear/Importar Key Pair** en AWS Console (ej: `mi-key.pem`).  
2. AWS almacena la **clave pública** en la instancia EC2 (en `~/.ssh/authorized_keys`).  
3. El usuario accede via SSH usando la **clave privada** (ej: `ssh -i mi-key.pem ec2-user@ip-publica`).  

### **Recomendaciones de Seguridad**  
- 🚫 **Nunca subir claves privadas a GitHub/GitLab**.  
- 🔐 **Usar AWS Systems Manager (SSM)** como alternativa a SSH.  
- ⚠️ **No hay recuperación**: Si pierdes la clave privada, deberás crear una nueva instancia.  

### **Ejemplo: Consola AWS**  
```markdown
![Key Pair en AWS Console](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/key-pair-import.png "Importar Key Pair")
```

---

## **Resumen Final**  
### **Tabla Comparativa: Temas Clave**  
| **Concepto**          | **Beneficios**                              | **Casos de Uso**                          |
|-----------------------|--------------------------------------------|------------------------------------------|
| **EBS Multi-Attach** | Alta disponibilidad para aplicaciones clusterizadas. | Bases de datos (Oracle RAC, SAP HANA). |
| **Cifrado EBS**      | Cumplimiento de normas (HIPAA, GDPR).      | Sistemas con datos sensibles.           |
| **Key Pairs**        | Mayor seguridad vs. contraseñas.           | Administración remota de instancias.    |

### **Próximos Pasos**  
En el laboratorio práctico:  
1. Crearemos un volumen EBS cifrado.  
2. Configuraremos Multi-Attach.  
3. Accederemos a una instancia EC2 via SSH usando Key Pairs.  
