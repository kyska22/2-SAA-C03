# 📬 BLOQUE: Mensajería e Integraciones

| Tema/Herramienta | Concepto breve | Palabras clave para el examen | Ejemplo de uso |
|:---|:---|:---|:---|
| Amazon SNS (Simple Notification Service) | Servicio de mensajería tipo "pub/sub" para enviar notificaciones de manera masiva. | SNS, Pub/Sub, Push Notification | Enviar alertas automáticas por SMS cuando un sistema falla. |
| Amazon SQS (Simple Queue Service) | Servicio de colas para desacoplar componentes de una aplicación. | SQS, Queue, Message Decoupling | Colocar pedidos de e-commerce en cola para procesarlos asíncronamente. |
| Amazon MQ | Servicio de broker de mensajes basado en Apache ActiveMQ o RabbitMQ. | MQ, ActiveMQ, RabbitMQ, Broker | Migrar una aplicación tradicional que usa ActiveMQ a la nube. |
| Introducción a Integração e Mensageria da AWS | Servicios que facilitan la comunicación asincrónica y desacoplada entre sistemas. | Messaging, Decoupling, Event-Driven | Usar SNS para notificar y SQS para procesamiento de pedidos. |
| AWS Step Functions | Servicio para coordinar flujos de trabajo usando estados y tareas. | Step Functions, Orchestration, Workflow | Orquestar un proceso de aprobación de documentos entre varios sistemas. |
| Ordenação de Dados no Kinesis e SQS | Kinesis permite ordenación estricta de eventos, SQS FIFO mantiene orden dentro de colas. | Kinesis Ordering, SQS FIFO | Usar SQS FIFO para procesar pedidos de manera secuencial. |
| Comparação entre SQS, SNS e Kinesis | Comparar modelos de entrega de mensajes: colas, pub/sub y procesamiento de streams. | SQS vs SNS vs Kinesis, Messaging Models | Usar SNS para notificar múltiples servicios y SQS para procesamiento controlado. |

---
