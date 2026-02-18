# 🤖 Clasificador Inteligente de Leads con LLM (n8n)

¡Bienvenido! Este es un sistema de automatización de nivel profesional desarrollado en **n8n**. El flujo no solo recibe mensajes, sino que utiliza **IA (Llama 3.3 vía Groq)** para realizar un análisis de sentimiento, priorizar la atención y ejecutar acciones automáticas según la urgencia del cliente.

## 🚀 ¿Qué hace este Workflow?

El sistema actúa como un "Triaje" inteligente para cualquier negocio:
1.  **Ingesta:** Recibe datos de contacto mediante un Webhook.
2.  **Análisis (LLM):** Clasifica el tono, la intención y la prioridad del mensaje.
3.  **Ruteo Inteligente:**
    * **Prioridad Alta 🔴:** Notifica al equipo por Gmail y lo registra como urgente.
    * **Prioridad Media 🟡:** La IA redacta y envía una respuesta automática personalizada.
    * **Prioridad Baja 🟢:** Registra el lead y programa un seguimiento diferido.

## 🛠️ Stack Tecnológico

* **Orquestador:** [n8n](https://n8n.io/)
* **IA (LLM):** Llama-3.3-70b-versatile (vía **Groq** para baja latencia).
* **Integraciones:** Gmail, Google Sheets.
* **Lógica:** LangChain Nodes & JavaScript.

## 📋 Estructura de Datos (Google Sheets)

Para que el flujo funcione, necesitás un archivo de Google Sheets con tres hojas (`Alta`, `Media`, `Baja`) y las siguientes columnas:

| Columna | Descripción |
| :--- | :--- |
| `nombre` | Nombre del lead |
| `mail` | Correo electrónico |
| `mensaje` | Consulta original |
| `prioridad` | Clasificación (Alta/Media/Baja) |
| `tono` | Sentimiento detectado |
| `duda` | Resumen de la duda (max 5 palabras) |

## 🧠 Ingeniería de Prompts (System Prompts)

El "cerebro" del sistema utiliza prompts optimizados para evitar alucinaciones:

> *"Actúa como un analista profesional de atención al cliente. Clasificar el tono (Enojado, Neutral, Entusiasmado) e identificar la prioridad basándote en la urgencia y el riesgo de cancelación."*

## ⚙️ Configuración e Instalación

1.  **Importar:** Descargá el archivo `.json` de este repositorio e importalo en tu instancia de n8n.
2.  **Credenciales:**
    * Configurá tu API Key de **Groq**.
    * Vinculá tu cuenta de **Gmail** (OAuth2).
    * Conectá tu **Google Sheets**.
3.  **Webhook:** Copiá la URL de "Production Webhook" y configurala en tu formulario o aplicación de origen.

## ⚠️ Notas de Seguridad

* Este JSON **no contiene credenciales reales**, solo identificadores de referencia.
* Asegúrate de cambiar los correos electrónicos de destino (`eliaselado1715@gmail.com`) por los tuyos antes de ejecutar.

---
**Desarrollado por:** Elias  
**Licencia:** MIT
<img width="1254" height="444" alt="image" src="https://github.com/user-attachments/assets/67bbf144-80bf-4d13-9a4a-372a8a32c21e" />



