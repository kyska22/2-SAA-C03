# 🌐 BLOQUE: Redes y Conectividad

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Amazon VPC (Componentes & Estructura) | Permite crear redes virtuales aisladas dentro de AWS. | VPC, Subnets, Routing Tables | Crear una VPC con subredes públicas y privadas para una aplicación web segura. |
| VPC Sub-Redes | Dividen la VPC en segmentos lógicos para controlar acceso y disponibilidad. | Subnet, Public vs Private | Subred pública para servidores web y privada para bases de datos. |
| IP Privado vs Público | IP pública permite acceso externo; IP privada solo dentro de la VPC. | Public IP, Private IP | Asignar IP privada a base de datos y pública a servidor web. |
| Tabelas de Rotas | Definen cómo se enrutan los paquetes dentro de la VPC. | Routing Table, Route | Crear ruta para que subred privada acceda a internet a través de NAT. |
| Internet Gateway | Permite que instancias en la VPC se comuniquen con internet. | Internet Gateway, IGW | Asociar un IGW a una VPC para acceso público desde instancias. |
| Elastic Network Interface (ENI) | Tarjeta de red virtual que puedes adjuntar a instancias EC2. | ENI, Multiple IPs, Elasticity | Adjuntar múltiples ENI a una instancia EC2 para alta disponibilidad de red. |
| IP Elástico (Elastic IP) | IP pública fija que puedes asociar a una instancia EC2. | Elastic IP, Static Public IP | Usar Elastic IP para mantener la misma IP después de reiniciar EC2. |
| NAT Gateway | Permite que instancias en subredes privadas accedan a internet de forma segura. | NAT Gateway, Private Subnet Internet Access | Permitir actualizaciones de software en instancias privadas sin exponerlas. |
| Bastion Hosts | Servidor seguro que permite acceso SSH/RDP a instancias en subredes privadas. | Bastion Host, Jump Box | Acceder a servidores privados a través de un bastion host controlado. |
| VPC Peering | Conecta dos VPCs para comunicarse usando IPs privadas. | VPC Peering, Private Communication | Permitir comunicación entre dos VPCs en diferentes cuentas. |
| AWS Transit Gateway | Conecta múltiples VPCs y redes locales a través de un solo gateway. | Transit Gateway, Hub-and-Spoke | Centralizar la conectividad de múltiples VPCs a redes locales. |
| VPC Endpoints | Permiten el acceso privado a servicios de AWS desde tu VPC sin usar internet. | VPC Endpoint, PrivateLink, Interface Endpoint | Acceder a S3 desde una VPC sin pasar por internet. |
| VPC Flow Logs | Capturan información sobre el tráfico IP que entra o sale de interfaces de red. | Flow Logs, Network Monitoring | Monitorear el tráfico hacia una instancia EC2 para auditorías de seguridad. |
| AWS Site-to-Site VPN | Conexión segura entre una red on-premises y AWS sobre Internet. | VPN, Site-to-Site | Conectar el datacenter corporativo a AWS para migrar cargas de trabajo. |
| AWS VPN CloudHub | Permite conectar múltiples redes on-premises a AWS mediante VPNs. | VPN CloudHub, Multi-Site VPN | Conectar sucursales a través de AWS de manera segura. |
| AWS Direct Connect | Conexión privada dedicada entre tu red y AWS. | Direct Connect, Private Connection | Mejorar la velocidad y la seguridad de transferencia de datos pesados. |

---
