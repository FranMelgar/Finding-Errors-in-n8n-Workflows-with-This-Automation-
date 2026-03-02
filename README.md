🐾 Descripción

Este proyecto implementa un generador automático de historias cortas sobre animales utilizando inteligencia artificial y automatización con n8n.

El sistema ejecuta tareas programadas que crean contenido creativo mediante OpenAI y añade un workflow independiente de monitoreo que detecta errores y envía alertas por email.

⚙️ Arquitectura

El proyecto está compuesto por dos workflows principales:

Animal Story → generación automática de contenido.

Error Workflow Trigger → sistema centralizado de monitoreo y alertas.

Esto simula una arquitectura real de producción con observabilidad básica.

🧠 Workflow 1 — Animal Story
🔄 Funcionamiento

Schedule Trigger

Ejecuta el workflow automáticamente cada 1 minuto.

Permite generación continua de contenido.

AI Agent

Recibe la instrucción de crear historias cortas sobre animales.

Genera contenido creativo usando IA.

OpenAI Chat Model

Modelo: gpt-4o-mini

Produce historias breves optimizadas para velocidad y costo.

✨ Características

Generación automática de contenido creativo

Ejecución programada (cron automation)

Uso de agentes de IA en n8n

Workflow totalmente autónomo

🚨 Workflow 2 — Error Monitoring System
🎯 Objetivo

Detectar automáticamente cualquier fallo en workflows y notificar al usuario con información técnica detallada.

🔍 Funcionamiento

Error Trigger

Se activa cuando cualquier workflow configurado falla.

Gmail Node

Envía un email automático con:

Nombre del workflow afectado

Fecha y hora del error

Último nodo ejecutado

Mensaje de error

Stack trace completo

Esto permite debugging rápido sin revisar manualmente n8n.

📧 Ejemplo de alerta enviada
Workflow Animal Story failed

Date and time: [timestamp]
Last Node: AI Agent

Details: [error message]

Error Stack: [stack trace]
🧰 Tecnologías utilizadas

n8n

OpenAI API

GPT-4o-mini

Gmail API (OAuth2)

Automatización programada (Schedule Trigger)

Error Handling Workflows

🚀 Casos de uso

Generación automática de contenido

Bots creativos

Automatizaciones programadas

Sistemas de monitoreo de workflows

Alertas automáticas de fallos

🛠️ Requisitos

n8n instalado (cloud o self-hosted)

API Key de OpenAI

Cuenta Gmail con OAuth2 configurado

▶️ Instalación

Importar ambos workflows en n8n.

Configurar credenciales:

OpenAI

Gmail OAuth2

Asociar el Error Workflow como workflow de errores.

Activar los workflows.

El sistema comenzará a ejecutarse automáticamente.

📌 Notas técnicas

El manejo de errores está desacoplado del workflow principal.

Permite reutilizar el mismo sistema de alertas en múltiples automatizaciones.

Diseño inspirado en prácticas reales de monitoreo en producción.
