# 🗄️ BLOQUE: Almacenamiento

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Amazon S3 Avanzado | Almacenamiento de objetos con características avanzadas (ciclo de vida, notificaciones, etc.). | S3 Lifecycle, Event Notifications, S3 Select | Configurar ciclo de vida para archivar archivos antiguos en Glacier. |
| Clases de Armazenamento S3 | Diferentes niveles de almacenamiento optimizados para costo y acceso. | S3 Standard, IA, Glacier, Glacier Deep Archive | Usar S3 IA para respaldos poco accedidos. |
| Ciclo de Vida (Lifecycle) | Política para mover objetos automáticamente entre clases de almacenamiento o eliminarlos. | Lifecycle Policy, Transition, Expiration | Configurar objetos de S3 para archivarse tras 30 días. |
| Requester Pays | Configura un bucket donde el solicitante paga la descarga de datos. | Requester Pays, S3 Bucket | Cobrar a terceros que acceden a tus datos públicos en S3. |
| Notificaciones de Eventos | Eventos de S3 que activan acciones, como invocar Lambda. | S3 Event Notification, Lambda Trigger | Activar un Lambda cuando se sube un archivo a S3. |
| Performance en S3 | Mejores prácticas para lograr rendimiento óptimo (multi-part upload, paralelismo). | S3 Performance, Parallel Uploads | Usar carga multiparte para grandes archivos de video. |
| S3 CORS | Permite solicitudes de otros dominios a tu bucket S3. | CORS, Cross-Origin, S3 | Permitir que un sitio web acceda a imágenes desde un bucket S3. |
| Select & Glacier Select | Permiten consultar directamente datos en S3 o Glacier sin descargarlos completos. | S3 Select, Glacier Select, SQL Queries | Extraer solo ciertos campos de archivos CSV en S3 usando S3 Select. |
| S3 Operações Batch | Permite ejecutar acciones masivas (como copiar o etiquetar objetos) sobre muchos objetos S3. | S3 Batch Operations, Bulk Actions | Actualizar el almacenamiento clase de miles de objetos a IA. |
| Glacier Vault Lock | Configura políticas de retención inmutables en Glacier Vaults. | Glacier Vault Lock, Retention Policy | Crear un vault para archivado legal de registros médicos. |
| Access Point S3 | Puntos de acceso administrados individualmente para buckets S3. | S3 Access Point, Access Management | Crear access points para diferentes aplicaciones usando el mismo bucket. |
| Amazon FSx | Sistemas de archivos gestionados para Windows, Lustre, NetApp, OpenZFS. | FSx for Windows, FSx for Lustre, FSx NetApp | Usar FSx for Lustre para cargas HPC de alto rendimiento. |
| AWS Storage Gateway | Conecta almacenamiento on-premises a AWS usando servicios de archivo, volumen y cinta virtual. | Storage Gateway, On-Premises, Backup | Configurar File Gateway para respaldos automáticos en S3. |
| AWS DataSync | Servicio para mover grandes cantidades de datos entre on-premises y AWS. | DataSync, Data Transfer, Migration | Migrar repositorios de archivos locales a EFS usando DataSync. |
| AWS Transfer Family | Servicio que permite la transferencia de archivos directamente a S3 usando SFTP, FTPS o FTP. | Transfer Family, SFTP, FTP to S3 | Permitir transferencias SFTP de socios a un bucket S3 seguro. |

---
