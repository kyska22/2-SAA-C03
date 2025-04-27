# 🖥️ BLOQUE: Cómputo

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Amazon EC2 (Associate) | Servicio que permite lanzar servidores virtuales configurables en la nube. | EC2, Instancia, Tipos de Instancia | Lanzar instancia EC2 optimizada para cómputo (C6i). |
| Grupos de Posicionamiento | Controlan la ubicación física de instancias EC2 para mejorar disponibilidad o rendimiento. | Placement Group, Cluster, Spread, Partition | Usar Cluster Placement Group para baja latencia en HPC. |
| EC2 Armazenamento | Opciones de almacenamiento para instancias EC2 (EBS, Instance Store). | EBS, Instance Store, Armazenamiento | Usar EBS como volumen persistente para EC2. |
| Tipos de Volumen - EBS Multi-Attach y Criptografía | Permite a varios EC2 montar un mismo volumen EBS, y soporta cifrado de datos en reposo. | Multi-Attach, Encryption, KMS | Crear volumen EBS cifrado y conectado a varias instancias. |
| Outros tipos de armazenamento EBS | General Purpose, Provisioned IOPS, Throughput Optimized, Cold HDD. | gp3, io2, st1, sc1 | Escoger io2 para una base de datos crítica. |
| Amazon EFS | Sistema de archivos elástico y escalable para EC2, montado en múltiples instancias. | EFS, NFS, Compartido | Compartir archivos entre varias instancias web EC2. |
| EBS vs EFS | Comparación entre almacenamiento de bloques (EBS) y almacenamiento de archivos (EFS). | EBS = Bloques, EFS = Archivos | Usar EBS para bases de datos y EFS para contenido compartido. |
| EC2 Hibernate | Permite pausar una instancia EC2 y retomarla conservando el estado en disco. | Hibernate, Fast Boot | Hibernar instancias de desarrollo fuera de horario laboral. |
| AWS App Runner | Servicio para desplegar aplicaciones web y APIs directamente desde el código o contenedores sin administrar servidores. | App Runner, Serverless Apps | Desplegar una app Flask directamente desde GitHub. |
| Serverless en AWS | Ejecutar aplicaciones sin necesidad de administrar servidores (ej. AWS Lambda). | Lambda, Serverless, Escalado Automático | Crear función Lambda para procesamiento de imágenes. |
| CloudFront Functions y Lambda@Edge | Ejecutar funciones ligeras cerca del usuario en los Edge Locations. | CloudFront, Edge Computing, Lambda@Edge | Reescribir URLs en solicitudes de CDN antes de llegar a origen. |
| Integración de AWS Lambda con Otros Servicios | Lambda puede ser disparado por eventos de S3, DynamoDB, API Gateway, entre otros. | Lambda Trigger, Event-Driven | Ejecutar Lambda al cargar archivo en un bucket S3. |

---
