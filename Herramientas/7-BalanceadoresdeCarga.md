# ⚙️ BLOQUE: Cómputo y Balanceo de Carga

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Amazon EC2 (Associate) | Servicio que proporciona capacidad de cómputo escalable en la nube. | EC2, Instancias, Compute | Implementar una aplicación web en instancias EC2 para manejar el tráfico de usuarios. |
| Auto Scaling Group | Permite ajustar automáticamente la cantidad de instancias EC2 según la demanda. | Auto Scaling, Escalado automático | Aumentar instancias EC2 durante picos de tráfico y reducirlas en horas de baja demanda. |
| Elastic Load Balancer (ELB) | Distribuye automáticamente el tráfico de entrada entre múltiples destinos. | ELB, Load Balancer, Distribución de tráfico | Balancear el tráfico de una aplicación web entre varias instancias EC2. |
| Health Checks | Monitorean la salud de las instancias y redirigen el tráfico solo a las saludables. | Health Check, Monitoreo de salud | Detectar y reemplazar instancias EC2 no saludables automáticamente. |
| Tipos de Balanceadores | Diferentes tipos de ELB: Application, Network y Gateway Load Balancer. | ALB, NLB, GLB | Usar ALB para aplicaciones web y NLB para aplicaciones que requieren baja latencia. |
| Application Load Balancer (ALB) | Balanceador de carga a nivel de aplicación que opera en la capa 7 del modelo OSI. | ALB, Capa 7, HTTP/HTTPS | Dirigir solicitudes HTTP a diferentes servicios basados en la ruta URL. |
| Network Load Balancer (NLB) | Balanceador de carga a nivel de red que opera en la capa 4 del modelo OSI. | NLB, Capa 4, TCP/UDP | Manejar millones de solicitudes por segundo con baja latencia. |
| Sticky Sessions | Permiten que un usuario sea dirigido siempre a la misma instancia durante una sesión. | Sticky Sessions, Sesiones persistentes | Mantener la sesión de un usuario en la misma instancia EC2 para aplicaciones con estado. |
| Cross-Zone Load Balancing | Distribuye el tráfico de manera uniforme entre instancias en diferentes zonas de disponibilidad. | Cross-Zone, Balanceo entre zonas | Mejorar la disponibilidad distribuyendo el tráfico entre múltiples zonas. |
| Route 53 | Servicio de DNS escalable y altamente disponible. | Route 53, DNS, Enrutamiento | Traducir nombres de dominio a direcciones IP para acceder a recursos en AWS. |
| Route 53 (Políticas de Roteamento) | Permite controlar cómo se enruta el tráfico a través de diferentes políticas. | Routing Policies, Latency, Weighted | Usar enrutamiento basado en latencia para dirigir a los usuarios al servidor más cercano. |
| AWS API Gateway | Servicio para crear, publicar y mantener APIs a cualquier escala. | API Gateway, REST, WebSocket | Exponer una API RESTful para una aplicación móvil. |

---
