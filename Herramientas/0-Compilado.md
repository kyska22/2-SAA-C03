**Guia de Conceptos, Herramientas y Ejemplos para Certificacion AWS Solutions Architect (Español)**

---

# Infraestructura y Redes

| Tema/Herramienta                 | Concepto breve                                                    | Palabras clave para el examen                              | Ejemplo de uso                                                            |
| -------------------------------- | ----------------------------------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------- |
| Infraestructura Global AWS       | Red mundial de regiones y AZs.                                    | Regiones, Zonas de Disponibilidad (AZ), Edge Locations     | Desplegar una aplicación en varias regiones para alta disponibilidad.     |
| Servicios Globales vs Regionales | Algunos servicios operan globalmente, otros dentro de una región. | Global vs Regional, Ejemplos: IAM (global), EC2 (regional) | IAM gestiona usuarios globalmente; EC2 se despliega por región.           |
| VPC                              | Red virtual privada para lanzar recursos de AWS.                  | VPC, Subredes, Seguridad                                   | Crear una VPC aislada para una aplicación interna.                        |
| Subredes                         | Dividen la VPC en bloques de red más pequeños.                    | Subnets, Public/Private                                    | Subred pública para servidores web, privada para bases de datos.          |
| IP Privado vs Público            | IP privada: acceso interno; IP pública: acceso externo.           | Private IP, Public IP                                      | Asignar IP privada a una instancia de backend.                            |
| Tabelas de Rotas                 | Definen cómo fluye el tráfico de red dentro de la VPC.            | Route Tables, Routing                                      | Redirigir tráfico de subred privada a NAT Gateway.                        |
| Internet Gateway                 | Permite la comunicación entre la VPC y internet.                  | IGW, Internet Access                                       | Conectar instancias públicas a internet.                                  |
| Elastic Network Interface        | Interface de red virtual para instancias EC2.                     | ENI, Network Interface                                     | Adjuntar una ENI secundaria a una instancia EC2 para alta disponibilidad. |
| IP Elástico                      | IP fija y pública que puedes mover entre instancias.              | Elastic IP, IP Estatica                                    | Recuperar rápidamente de fallos reasignando IP elástica.                  |
| NAT Gateway                      | Permite que instancias privadas accedan a internet saliente.      | NAT, Outbound Traffic                                      | Dar actualizaciones a servidores backend sin exponerlos.                  |
| VPC Peering                      | Conexión privada entre dos VPCs.                                  | VPC Peering, Private Connectivity                          | Conectar aplicaciones entre VPCs sin salir a internet.                    |
| AWS Transit Gateway              | Conecta múltiples VPCs y redes on-premises.                       | Transit Gateway, Hub Network                               | Centralizar la conectividad entre varias VPCs.                            |
| VPC Endpoints                    | Acceso privado a servicios AWS desde VPC.                         | VPC Endpoints, PrivateLink                                 | Acceso a S3 sin pasar por internet.                                       |
| VPC Flow Logs                    | Captura información sobre el tráfico de red de la VPC.            | Flow Logs, Network Monitoring                              | Analizar patrones de tráfico para seguridad.                              |

# Computo y Balanceo de Carga

| Tema/Herramienta          | Concepto breve                                     | Palabras clave para el examen        | Ejemplo de uso                                  |
| ------------------------- | -------------------------------------------------- | ------------------------------------ | ----------------------------------------------- |
| Amazon EC2 (Associate)    | Capacidad de cómputo escalable en la nube.         | EC2, Compute, Instancias             | Lanzar servidores de aplicación web.            |
| Auto Scaling Group        | Ajusta número de instancias según demanda.         | Auto Scaling, Elasticidad            | Aumentar instancias en horas pico.              |
| Elastic Load Balancer     | Balancea tráfico entrante entre instancias.        | ELB, Load Balancer                   | Distribuir solicitudes entre varias EC2.        |
| Health Checks             | Verifica estado de instancias.                     | Health Check, Monitoring             | Remover instancias no saludables.               |
| Application Load Balancer | Balanceador de carga a nivel de aplicación.        | ALB, Layer 7                         | Redirigir tráfico basado en URL.                |
| Network Load Balancer     | Balanceador de carga de red, capa 4.               | NLB, TCP, Low Latency                | Aplicaciones de alta performance.               |
| Sticky Sessions           | Mantienen sesión de usuario en la misma instancia. | Sticky Sessions, Session Persistence | Aplicaciones con sesión de usuario persistente. |
| Cross-Zone Load Balancing | Distribuye tráfico entre zonas.                    | Cross-Zone, HA                       | Mejorar tolerancia a fallos.                    |
| Route 53                  | Servicio DNS de alta disponibilidad.               | Route 53, DNS, Latency Routing       | Resolver nombres de dominio a IP.               |
| AWS API Gateway           | Servicio para construir APIs seguras.              | API Gateway, REST APIs               | Crear backend serverless para móviles.          |

# Seguridad y Gestão de Identidad

| Tema/Herramienta                            | Concepto breve                                         | Palabras clave para el examen             | Ejemplo de uso                                     |
| ------------------------------------------- | ------------------------------------------------------ | ----------------------------------------- | -------------------------------------------------- |
| AWS IAM                                     | Administra acceso seguro a recursos.                   | IAM, Policies, Identity Management        | Crear políticas de acceso basadas en roles.        |
| IAM Condiciones                             | Reglas adicionales en las políticas.                   | IAM Conditions                            | Restringir acceso por IP.                          |
| IAM Roles vs Políticas Basadas en Recursos  | Roles delegan permisos; políticas protegen recursos.   | IAM Roles, Resource Policies              | Lambda accede a S3 mediante rol.                   |
| Limites de Permissões do IAM                | Restringe permisos máximos.                            | IAM Permissions Boundaries                | Control de privilegios de usuarios.                |
| Amazon S3 Seguridad (Criptografía)          | Protege datos en S3 con cifrado.                       | S3 Encryption, SSE, KMS                   | Cifrado automático de objetos.                     |
| MFA Delete, Logs de Acceso, Pre-Signed URLs | MFA protege borrado; logs monitorean; URLs temporales. | MFA Delete, Access Logs                   | URL firmada para descarga segura.                  |
| AWS Secrets Manager                         | Gestiona secretos de forma segura.                     | Secrets Manager, Secret Rotation          | Guardar contraseñas de bases de datos.             |
| AWS Certificate Manager                     | Gestiona certificados SSL/TLS.                         | ACM, SSL/TLS                              | HTTPS para aplicaciones web.                       |
| AWS WAF                                     | Firewall para proteger aplicaciones web.               | WAF, OWASP Protections                    | Bloquear ataques de inyección SQL.                 |
| AWS Shield                                  | Protección contra ataques DDoS.                        | Shield, DDoS Protection                   | Mitigar ataque DDoS automáticamente.               |
| AWS Firewall Manager                        | Gestor centralizado de reglas WAF y Shield.            | Firewall Manager, Policy Management       | Unificar reglas de seguridad en múltiples cuentas. |
| Amazon GuardDuty                            | Detección de amenazas y anomalías.                     | GuardDuty, Threat Detection               | Detectar accesos maliciosos.                       |
| Amazon Inspector                            | Escaneo de vulnerabilidades automático.                | Inspector, Vulnerability Assessment       | Evaluar instancias EC2 contra vulnerabilidades.    |
| AWS Macie                                   | Descubrimiento de datos sensibles.                     | Macie, Sensitive Data Protection          | Encontrar datos PII en S3.                         |
| AWS Network Firewall                        | Firewall gestionado para VPC.                          | Network Firewall, Network Security        | Controlar tráfico entre subredes.                  |
| Amazon Cognito                              | Autenticación y gestión de usuarios.                   | Cognito, User Pools                       | Login social en apps móviles.                      |
| AWS IAM Identity Center                     | Gestión de acceso centralizado.                        | IAM Identity Center, SSO                  | Inicio de sesión único en AWS.                     |
| AWS KMS                                     | Servicio de gestión de claves.                         | KMS, Key Management Service               | Cifrar objetos S3.                                 |
| Parameter Store                             | Almacenamiento seguro de parámetros.                   | Parameter Store, Configuration Management | Gestionar configuración segura de apps.            |

---

# Resumen: Palabras Clave más Frecuentes en Exámenes AWS

- IAM, Roles, Policies, Conditions
- EC2, Auto Scaling, ELB (ALB/NLB)
- VPC, Subnets, Route Tables, IGW, NAT Gateway
- S3, Encryption, Lifecycle, CORS
- Route 53, Routing Policies, DNS
- Secrets Manager, KMS, MFA Delete
- CloudWatch (Metrics, Alarms, Logs)
- CloudTrail, Config (Auditoría y monitoreo)
- RDS, Multi-AZ, Read Replicas
- SNS, SQS, Event-driven Architecture
- API Gateway, Lambda, Serverless
- Shield, WAF, Firewall Manager
- Cognito, Identity Center (SSO)
- Kinesis, SQS, SNS (mensajería y eventos)

---

