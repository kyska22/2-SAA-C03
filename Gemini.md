¡Excelente iniciativa! El examen AWS Certified Solutions Architect - Associate (SAA-C03) se centra mucho en el diseño de arquitecturas resilientes, de alto rendimiento, seguras y optimizadas en costos.
Para aprobar, no solo debes saber qué hace cada servicio, sino identificar el escenario específico que AWS plantea en la pregunta.
Aquí tienes los servicios "estrella" y las palabras clave que los delatan:
1. Computación (Compute)
| Servicio | Palabras Clave / Escenarios |
|---|---|
| EC2 Auto Scaling | "Scalability", "High Availability", "Maintain a fixed number of instances", "Varying load". |
| Lambda | "Serverless", "Event-driven", "Short execution time" (menos de 15 min), "Cost-effective for intermittent traffic". |
| AWS Fargate | "Serverless container", "No manage underlying infrastructure", "Microservices". |
2. Almacenamiento (Storage)
| Servicio | Palabras Clave / Escenarios |
|---|---|
| S3 (Standard) | "Object storage", "Durability", "Static website hosting". |
| S3 Glacier | "Archival", "Long-term storage", "Low cost", "Retrieval time (minutes/hours)". |
| EBS | "Block storage", "Single EC2 instance", "Database storage", "Persistence". |
| EFS | "Shared storage", "Linux instances", "NFS protocol", "Scalable throughput". |
| FSx for Windows | "SMB protocol", "Windows File Server", "Microsoft Active Directory integration". |
3. Bases de Datos (Databases)
| Servicio | Palabras Clave / Escenarios |
|---|---|
| RDS | "Relational", "SQL", "Complex joins", "Multi-AZ" (para alta disponibilidad), "Read Replicas" (para lectura masiva). |
| DynamoDB | "NoSQL", "Key-value", "Millisecond latency", "Serverless", "High scale". |
| Aurora | "PostgreSQL/MySQL compatible", "High performance", "Auto-scaling storage". |
| Redshift | "OLAP", "Data Warehouse", "Business Intelligence", "Complex analytical queries". |
| ElastiCache | "In-memory database", "Caching", "Reduce latency", "Redis or Memcached". |
4. Redes y Entrega de Contenido (Networking)
| Servicio | Palabras Clave / Escenarios |
|---|---|
| Route 53 | "DNS", "Health checks", "Failover routing", "Latency-based routing". |
| CloudFront | "CDN", "Edge locations", "Global users", "Static and dynamic content delivery". |
| Global Accelerator | "Static IP", "Non-HTTP traffic", "Improve global performance/latency". |
| VPC Peering | "Connect two VPCs", "No single point of failure", "Same or different accounts". |
| PrivateLink | "Expose service privately", "Avoid public internet", "Interface VPC Endpoint". |
5. Integración y Mensajería (Decoupling)
| Servicio | Palabras Clave / Escenarios |
|---|---|
| SQS | "Decouple", "Asynchronous", "Queue", "Buffering", "Loose coupling". |
| SNS | "Fan-out", "Pub/Sub", "Notifications", "Mobile push", "Email". |
| EventBridge | "Schema registry", "SaaS integration", "Scheduled events", "Serverless bus". |
💡 Tips de "Oro" para el examen:
 * Cost-Effective: Si la pregunta pide la opción más barata, busca S3 Intelligent-Tiering, Spot Instances (si la carga es interrumpible) o Lambda.
 * High Availability: Siempre busca soluciones que involucren Multi-AZ o Load Balancers.
 * Disaster Recovery: Aprende la diferencia entre Backup & Restore (barato/lento) y Pilot Light / Warm Standby (caro/rápido).
¿Te gustaría que hagamos un simulacro de 3 preguntas para ver cómo aplicarías estas palabras clave?
