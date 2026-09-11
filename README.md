# Checkpoint 4 - Integraciones Avanzadas

Proyecto realizado para el curso de **IA y Automatización**.

## Objetivo

Desarrollar un workflow en n8n capaz de procesar correos electrónicos e integrar diferentes servicios externos para automatizar la gestión inicial de contactos y notificaciones.

## Flujo implementado

El workflow realiza el siguiente proceso:

1. Recibe correos mediante **Email Trigger (IMAP)**.
2. Filtra respuestas automáticas mediante **IF - Anti Auto-Reply**.
3. Obtiene y normaliza los datos principales del correo.
4. Consulta **Salesforce** para comprobar si el contacto ya existe.
5. Si el contacto existe, actualiza su información.
6. Si no existe, crea un nuevo contacto.
7. Genera automáticamente un **borrador en Gmail** utilizando los datos del correo recibido.
8. Prepara un payload con remitente, asunto y contenido.
9. Envía una notificación a **Slack** indicando que el caso queda pendiente de aprobación humana.

## Integraciones utilizadas

- n8n
- Email / IMAP
- Salesforce API
- Gmail API
- Slack API

## Validación

Se realizó una prueba completa utilizando un correo de prueba con el asunto:

**Solicitud final de prueba**

Durante la ejecución se verificó correctamente:

- Recepción y procesamiento del correo.
- Búsqueda y creación/actualización del contacto en Salesforce.
- Creación automática del borrador en Gmail.
- Envío de la notificación correspondiente a Slack.
- Finalización exitosa del workflow.

## Evidencias

### Workflow completo en n8n

![Workflow n8n](01-workflow-n8n.png)

### Contacto en Salesforce

![Salesforce](02-salesforce-contacto.png)

### Notificación en Slack

![Slack](03-slack-notificacion.png)

### Borrador generado en Gmail

![Gmail](04-gmail-borrador.png)

## Archivo del workflow

El workflow completo exportado desde n8n se encuentra incluido en este repositorio en formato `.json`.

## Autor

**Máximo Moscoloni**
