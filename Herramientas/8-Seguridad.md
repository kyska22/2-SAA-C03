# 🔐 BLOQUE: Seguridad y Gestión de Identidad

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| AWS IAM | Servicio que administra el acceso a los recursos de AWS de forma segura. | IAM, Gestión de Identidad, Permisos | Crear políticas de acceso para permitir que los usuarios accedan solo a S3. |
| IAM Condiciones | Permiten agregar reglas adicionales a las políticas de acceso. | IAM Conditions, Condicional Access | Permitir acceso a S3 solo desde direcciones IP específicas. |
| IAM Roles vs Políticas Basadas en Recursos | IAM Roles otorgan permisos a entidades; políticas basadas en recursos controlan acceso directamente en recursos. | IAM Roles, Resource Policies | Un Lambda accede a DynamoDB usando un IAM Role. |
| Limites de Permissões do IAM | Controla la cantidad máxima de permisos que un usuario o rol puede tener. | Permissions Boundary, IAM Limits | Restringir el máximo nivel de acceso que un desarrollador puede asumir. |
| Amazon S3 Seguridad (Criptografía) | S3 permite cifrar datos en reposo y en tránsito. | S3 Encryption, SSE, Client-side Encryption | Habilitar SSE-S3 para cifrar objetos automáticamente al almacenarlos en S3. |
| MFA Delete, Logs de Acesso, URLs Pré-Assinadas | MFA Delete protege la eliminación de objetos; Logs registran accesos; URLs firmadas permiten acceso temporal. | MFA Delete, Access Logs, Pre-Signed URLs | Generar URL firmada para acceso temporal a un archivo privado. |
| AWS Secrets Manager | Servicio para almacenar y rotar secretos (contraseñas, tokens) de manera segura. | Secrets Manager, Secret Rotation | Gestionar contraseñas de bases de datos de forma automática y segura. |
| AWS Certificate Manager (ACM) | Administra certificados SSL/TLS para proteger sitios web y aplicaciones. | ACM, SSL/TLS Certificates | Implementar HTTPS en un sitio web alojado en EC2 usando ACM. |
| AWS WAF | Firewall de aplicaciones web que ayuda a proteger contra exploits comunes. | WAF, Web Application Firewall, OWASP | Bloquear ataques de inyección SQL en aplicaciones web. |
| AWS Shield | Servicio de protección contra ataques DDoS. | Shield, DDoS Protection | Proteger una aplicación web de ataques de denegación de servicio distribuidos. |
| AWS Firewall Manager | Servicio centralizado para administrar reglas de WAF y Shield en varias cuentas. | Firewall Manager, Centralized Security | Configurar y aplicar políticas de firewall en múltiples cuentas AWS. |
| WAF vs Firewall Manager vs Shield | WAF protege aplicaciones, Shield protege contra DDoS, Firewall Manager gestiona políticas a escala. | WAF vs Shield vs Firewall Manager | Combinar servicios para proteger sitios críticos y administrar reglas desde un solo lugar. |
| Amazon GuardDuty | Servicio de detección de amenazas que monitorea actividad maliciosa. | GuardDuty, Threat Detection | Detectar accesos no autorizados en una cuenta AWS. |
| Amazon Inspector | Analiza vulnerabilidades y problemas de seguridad en instancias EC2. | Inspector, Vulnerability Scanning | Escanear instancias EC2 en busca de vulnerabilidades de seguridad. |
| AWS Macie | Servicio para descubrir y proteger datos confidenciales en S3. | Macie, Sensitive Data Discovery | Identificar archivos que contienen información personal en buckets S3. |
| Proteção de Rede na AWS (Security Groups y NACLs) | Seguridad a nivel de instancia (SG) y a nivel de subnet (NACLs). | Security Groups, NACLs, Network Security | Usar Security Groups para permitir solo tráfico HTTP y HTTPS hacia un servidor web. |
| AWS Network Firewall | Firewall administrado para proteger VPCs. | Network Firewall, VPC Firewall | Inspeccionar y filtrar tráfico dentro de una VPC para seguridad avanzada. |
| Amazon Cognito | Administra usuarios y autenticación en aplicaciones web y móviles. | Cognito, User Pools, Identity Pools | Implementar autenticación social (Google, Facebook) en una app móvil. |
| AWS IAM Identity Center (antes AWS SSO) | Gestión centralizada de acceso a múltiples cuentas AWS y aplicaciones. | IAM Identity Center, SSO | Permitir inicio de sesión único para múltiples cuentas AWS de manera centralizada. |
| AWS Security & Encryption - Introdução | Principios de protección de datos mediante cifrado, control de acceso y monitoreo. | Security, Encryption, Protection | Cifrar bases de datos, monitorear accesos y controlar permisos de usuarios. |
| AWS KMS (Key Management Service) | Servicio para administrar claves de cifrado. | KMS, Key Management, Encryption Keys | Cifrar datos sensibles almacenados en DynamoDB usando claves administradas. |
| Parameter Store | Almacena datos de configuración y secretos de forma segura para aplicaciones. | Parameter Store, Secure Parameters | Guardar contraseñas de bases de datos para ser accedidas por Lambda Functions. |

---
