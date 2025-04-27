# 📊 BLOQUE: Base de Datos y Análisis de Datos

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Banco de Dados (Tipos, Escolhendo Corretamente) | AWS ofrece varias opciones de bases de datos como relacionales y no relacionales. | RDS, DynamoDB, Aurora, ElastiCache | Elegir entre RDS y DynamoDB según la necesidad de la aplicación (relacional vs no relacional). |
| RDS - Serviço Gerenciado vs Não Gerenciado | RDS es un servicio completamente gestionado; no gestionado requiere intervención manual. | RDS, Managed, Unmanaged | Usar RDS para reducir la administración de bases de datos en producción. |
| RDS Scaling | Permite escalar una base de datos RDS hacia arriba o hacia abajo según la demanda. | RDS Scaling, Vertical Scaling, Horizontal Scaling | Aumentar la capacidad de almacenamiento y rendimiento de una base de datos RDS cuando aumenta la carga. |
| RDS Réplicas | Réplicas de lectura de RDS para distribuir la carga de lectura. | RDS Read Replicas, Replication | Crear réplicas de lectura en diferentes regiones para mejorar el rendimiento de lectura. |
| Multi-AZ | Implementa alta disponibilidad replicando RDS en múltiples zonas de disponibilidad. | Multi-AZ, High Availability | Implementar una base de datos RDS Multi-AZ para asegurar disponibilidad continua. |
| RDS Backups | RDS realiza backups automáticos y permite copias de seguridad manuales. | RDS Backups, Snapshots | Realizar backups periódicos para evitar la pérdida de datos en caso de fallo. |
| Amazon Aurora (Características) | Base de datos relacional de alto rendimiento compatible con MySQL y PostgreSQL. | Aurora, Relational, High Performance | Migrar bases de datos MySQL a Aurora para mejorar el rendimiento y reducir costos. |
| Aurora Serverless | Base de datos Aurora que ajusta automáticamente su capacidad según el tráfico. | Aurora Serverless, On-Demand Scaling | Usar Aurora Serverless para aplicaciones con tráfico impredecible que requieren escalabilidad automática. |
| Aurora Global | Aurora con capacidad multi-región para mejorar la disponibilidad global. | Aurora Global, Multi-Region | Configurar Aurora Global para que una base de datos esté disponible en múltiples regiones. |
| Amazon DynamoDB | Base de datos NoSQL completamente gestionada y escalable. | DynamoDB, NoSQL, Managed | Usar DynamoDB para aplicaciones móviles que requieren alta velocidad de lectura y escritura. |
| Amazon ElastiCache | Servicio de caché en memoria, compatible con Redis y Memcached. | ElastiCache, Redis, Memcached | Usar ElastiCache para mejorar el rendimiento de una aplicación web almacenando resultados de consultas frecuentes. |
| Amazon Neptune | Base de datos de gráficos optimizada para relaciones complejas entre datos. | Neptune, Graph Database, Relationships | Usar Neptune para almacenar y consultar datos de redes sociales o conexiones de personas. |
| Amazon Keyspaces (para Apache Cassandra) | Base de datos NoSQL compatible con Apache Cassandra. | Keyspaces, Cassandra, NoSQL | Usar Amazon Keyspaces para migrar datos de Cassandra a la nube con alta disponibilidad. |
| Amazon Kinesis | Plataforma para procesar y analizar grandes volúmenes de datos en tiempo real. | Kinesis, Streaming Data, Real-Time Analytics | Usar Kinesis para analizar datos de sensores en tiempo real en una aplicación IoT. |
| Ordenação de Dados no Kinesis e SQS | Kinesis garantiza el orden estricto de los eventos, SQS FIFO permite el orden en colas. | Kinesis Ordering, SQS FIFO, Message Order | Usar SQS FIFO para garantizar que los pedidos sean procesados en el orden correcto. |
| Comparação entre SQS, SNS e Kinesis | Comparar diferentes modelos de mensajería: SQS para colas, SNS para pub/sub y Kinesis para streams. | SQS vs SNS vs Kinesis, Messaging Models | Usar Kinesis para procesamiento de datos en tiempo real y SQS para manejo de tareas. |

---
