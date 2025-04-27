# **Conversión de Texto a Voz con Amazon Polly en AWS**

## **Introducción**
Amazon Polly es un servicio de **texto a voz (TTS)** basado en **aprendizaje profundo** que permite convertir texto en voz natural y realista. En este módulo, exploraremos cómo utilizar Polly desde la consola de AWS, configurar voces, formatos de salida y almacenar los resultados en **Amazon S3**.

---

## **Arquitectura del Proceso**
```
┌─────────────────────────────────────────────────────────────────┐
│                          Amazon Polly                           │
│  (Convierte texto en voz usando motores Neural o Standard)      │
└───────────────────────────────┬─────────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────────┐
│                          Amazon S3                              │
│  (Almacena archivos de audio en formato MP3, OGG, etc.)         │
└─────────────────────────────────────────────────────────────────┘
```

---

## **Configuración de Amazon Polly**
### **1. Acceso al Servicio**
1. **Iniciar Sandbox AWS**:
   - Visitar [whizlabs.com](https://whizlabs.com).
   - Seleccionar **"Start AWS Sandbox"** (entorno aislado de AWS).
   - Configurar tiempo de uso (ej: 1 hora).
   - Iniciar sesión en la consola con credenciales proporcionadas.

2. **Buscar Amazon Polly**:
   - En la barra de búsqueda de AWS, escribir **"Polly"**.
   - Seleccionar el servicio.

---

### **2. Parámetros de Conversión**
#### **Tabla de Opciones Disponibles**
| **Configuración**       | **Opciones**                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| **Motor de Voz**        | Neural (voz más natural) / Standard (calidad estándar)                     |
| **Idioma**              | Español, Inglés, Francés, Alemán, etc.                                     |
| **Voz**                 | Variantes masculinas/femeninas (ej: "Kimberly", "Mathis")                  |
| **Formato de Salida**   | MP3, OGG, PCM                                                              |
| **Método de Entrada**   | Texto plano / SSML (Speech Synthesis Markup Language)                       |

#### **Lista de Pasos para Generar Voz**
1. **Seleccionar motor** (Neural o Standard).
2. **Elegir idioma y voz**.
3. **Ingresar texto** (o usar SSML para mayor control).
4. **Previsualizar audio** (botón *"Listen"*).
5. **Descargar o guardar en S3**.

---

### **3. Ejemplo Práctico**
#### **Conversión de Texto a Voz**
1. **Texto de Ejemplo**:
   ```plaintext
   "Cloud computing es acceder a recursos IT a través de internet sin almacenar datos localmente. Los datos se guardan en centros de datos remotos."
   ```
2. **Configuración**:
   - Motor: **Neural**.
   - Voz: **Kimberly (Inglés)**.
   - Formato: **MP3**.

3. **Guardar en Amazon S3**:
   - Crear un bucket S3 (ej: `amazon-polly-demo`).
   - Hacer clic en *"Save to S3"* en Polly.

---

### **4. Personalización Avanzada**
#### **Opciones Adicionales**
- **Lexicons Personalizados**:
  - Permiten modificar la pronunciación de palabras específicas.
  - Se cargan en formato **XML**.
  ```xml
  <lexicon version="1.0">
      <lexeme><grapheme>AWS</grapheme><alias>Amazon Web Services</alias></lexeme>
  </lexicon>
  ```

- **SSML (Marcado de Voz)**:
  - Controla pausas, tono y velocidad.
  ```xml
  <speak>
      Esto es un <break time="500ms"/> ejemplo de SSML.
  </speak>
  ```

---

## **Comparativa: Neural vs Standard**
| **Característica**       | **Motor Neural**                          | **Motor Standard**                      |
|--------------------------|------------------------------------------|----------------------------------------|
| **Calidad de Voz**       | Más natural y humana                     | Natural pero menos realista            |
| **Idiomas Soportados**   | Limitados (inglés, español, etc.)       | Amplia variedad                        |
| **Latencia**             | Ligera mayor                             | Más rápida                             |
| **Costo**                | Más alto                                 | Económico                              |

---

## **Conclusión**
### **Beneficios de Amazon Polly**
✔ **Voces realistas** gracias a tecnología de **deep learning**.  
✔ **Integración con S3** para almacenamiento y reutilización.  
✔ **Personalización avanzada** con SSML y lexicons.  

### **Casos de Uso Comunes**
- **Asistentes virtuales** (Alexa, chatbots).
- **Audiolibros y podcasts automatizados**.
- **Sistemas IVR (Respuesta de Voz Interactiva)**.

---
### **Referencias**
- [Documentación Oficial de Amazon Polly](https://docs.aws.amazon.com/polly/latest/dg/what-is.html)  
- [Guía de SSML](https://developer.amazon.com/es-ES/docs/alexa/custom-skills/speech-synthesis-markup-language-ssml-reference.html)  
