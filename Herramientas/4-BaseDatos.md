# 🗃️ BLOQUE: Bases de Datos

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Banco de Dados na AWS (Review) | Revisión de los principales servicios de bases de datos administrados y no administrados en AWS. | RDS, DynamoDB, Aurora, Database | Elegir RDS para SQL estructurado y DynamoDB para NoSQL. |
| Banco de Dados (Tipos, Escolhendo Corretamente) | Evaluación de base de datos relacional vs NoSQL según el caso de uso. | Relacional vs NoSQL, Casos de Uso | Usar RDS MySQL para e-commerce y DynamoDB para sesiones web. |
| RDS - Servicio Gerenciado vs No Gerenciado | RDS administra backups, parches y alta disponibilidad automáticamente. | RDS Managed, Manual Database Management | Migrar base de datos on-premises a RDS para reducir operación manual. |
| RDS Scaling | Aumento de capacidad mediante replicas de lectura o aumento de instancia. | RDS Scaling, Read Replica, Vertical Scaling | Agregar Read Replica para manejar más lecturas en una aplicación. |
| RDS Réplicas | Réplicas de lectura permiten escalar la carga de consultas. | Read Replica, Multi-AZ | Crear réplicas para balancear lectura en una aplicación móvil. |
| Multi-AZ RDS | Replica sincrónica en otra zona de disponibilidad para alta disponibilidad. | Multi-AZ, High Availability | Proteger la base de datos de fallas en el AZ principal. |
| RDS Backups | RDS soporta backups automáticos y snapshots manuales. | Automated Backup, Snapshot | Restaurar base de datos a un punto anterior tras una corrupción de datos. |
| RDS & Aurora (Opción de Restauração) | Aurora ofrece restauración rápida de backups en segundos. | Aurora Restore, Backup Restore | Recuperar instancia Aurora de una falla lógica en minutos. |
| RDS & Aurora (Seguridad) | Incluye cifrado en reposo, en tránsito, IAM authentication y VPC security groups. | RDS Encryption, IAM DB Authentication | Usar conexión cifrada SSL para proteger datos en tránsito. |
| Amazon Aurora (Características) | Base de datos compatible con MySQL/PostgreSQL altamente disponible y escalable. | Aurora, Compatible MySQL/PostgreSQL, Performance | Migrar app crítica a Aurora para mayor desempeño y menor latencia. |
| Aurora Serverless | Versión de Aurora que escala automáticamente según demanda. | Aurora Serverless, Autoscaling | Usar Aurora Serverless para cargas intermitentes o impredecibles. |
| Aurora Global | Replica una base Aurora entre múltiples regiones para baja latencia global. | Global Database, Cross-Region Replication | Crear base de datos Aurora global para usuarios en Asia y Europa. |
| Aurora Machine Learning | Integración directa con servicios de ML como Amazon SageMaker. | Aurora ML Integration, ML Prediction | Hacer predicciones desde datos directamente en Aurora. |
| Aurora Backups | Copias de seguridad automáticas continuas sin impacto en rendimiento. | Continuous Backup, Restore | Recuperar datos Aurora en segundos tras eliminación accidental. |
| DocumentDB | Base de datos compatible con MongoDB, administrada por AWS. | DocumentDB, MongoDB Compatible | Migrar app basada en MongoDB a DocumentDB sin reescribir código. |
| ElastiCache (Características y Casos de Uso) | Servicio de cache administrado compatible con Redis y Memcached. | ElastiCache, Redis, Memcached | Acelerar respuestas de una API con caching Redis. |
| Amazon Neptune | Base de datos de grafos optimizada para consultas de relaciones complejas. | Neptune, Graph Database, RDF, Property Graph | Modelar redes sociales o relaciones entre entidades. |
| Amazon Keyspaces (para Apache Cassandra) | Servicio de base de datos compatible con Cassandra, totalmente administrado. | Keyspaces, Cassandra | Ejecutar cargas de trabajo de Cassandra sin gestionar infraestructura. |

---
