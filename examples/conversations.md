# Ejemplos de conversación / Example conversations

## Español

Estos ejemplos usan un evento ficticio llamado **Boda de Ana y Luis**. Cada uno muestra qué pedir, qué herramientas intervienen y qué resultado esperar.

### 1. Consultar un evento

**Lo que pides:**

> Busca Boda de Ana y Luis y muéstrame la tarjeta del evento.

**Herramientas:** `list_events`, `get_event`.

**Qué ves:** la tarjeta del evento con su información.

### 2. Crear un borrador con una plantilla

**Lo que pides:**

> Muéstrame las plantillas para crear Boda de Ana y Luis.

Después de elegir una:

> Usa esta plantilla para crear el borrador de la invitación.

**Herramientas:** `list_templates`, `create_event`.

**Qué ves:** el nuevo evento en borrador con la plantilla elegida.

### 3. Editar un texto

**Lo que pides:**

> En Boda de Ana y Luis, cambia el mensaje de los anfitriones por «Nos alegra compartir este día contigo». Conserva el resto de la invitación.

**Herramientas:** `list_events`, `get_event`, `update_event`.

**Qué ves:** el mensaje actualizado en la invitación, con el resto del contenido conservado.

### 4. Registrar una confirmación y preparar recordatorios

**Lo que pides:**

> Muéstrame los invitados de Boda de Ana y Luis. Lucía me confirmó que va a asistir; registra su confirmación y dame un resumen de las respuestas.

Después:

> Muéstrame los recordatorios y prepara los de quienes siguen pendientes de confirmar para que yo los comparta.

**Herramientas:** `list_guests`, `rsvp_guest`, `rsvp_summary`, `list_reminders`, `prepare_reminders`.

**Qué ves:** la confirmación registrada, el resumen de respuestas y los recordatorios preparados para compartir.

### 5. Publicar y volver a borrador

**Lo que pides:**

> Quiero publicar Boda de Ana y Luis. Pídeme confirmación antes de hacerlo.

Cuando el asistente te pida confirmación:

> Sí, publícala.

Para volver a borrador:

> Quiero volver a ponerla en borrador. Pídeme confirmación antes de cambiarla.

Cuando el asistente te pida confirmación:

> Sí, vuelve a dejarla en borrador.

**Herramientas:** `publish_event`, `unpublish_event`.

**Qué ves:** la invitación publicada tras tu confirmación y, después de la segunda confirmación, de nuevo en borrador.

## English

These examples use a fictional event called **Ana and Luis's Wedding**. Each one shows what to ask, the tools involved and the result to expect.

### 1. View an event

**What you ask:**

> Find Ana and Luis's Wedding and show me its event card.

**Tools:** `list_events`, `get_event`.

**What you see:** the event card with its information.

### 2. Create a draft from a template

**What you ask:**

> Show me templates for Ana and Luis's Wedding.

After choosing one:

> Use this template to create the invitation draft.

**Tools:** `list_templates`, `create_event`.

**What you see:** a new draft event using your chosen template.

### 3. Edit some text

**What you ask:**

> For Ana and Luis's Wedding, change the hosts' message to “We're so glad to share this day with you.” Keep the rest of the invitation as it is.

**Tools:** `list_events`, `get_event`, `update_event`.

**What you see:** the updated message in the invitation, with the rest of the content preserved.

### 4. Record an RSVP and prepare reminders

**What you ask:**

> Show me the guests for Ana and Luis's Wedding. Lucía told me she's coming; record her RSVP and give me a summary of the responses.

Then:

> Show me the reminders and prepare reminders for guests who still need to reply, so I can share them.

**Tools:** `list_guests`, `rsvp_guest`, `rsvp_summary`, `list_reminders`, `prepare_reminders`.

**What you see:** the recorded RSVP, a response summary and reminders ready for you to share.

### 5. Publish and return to draft

**What you ask:**

> I'd like to publish Ana and Luis's Wedding. Ask me to confirm before you do.

When the assistant asks for confirmation:

> Yes, publish it.

To return to draft:

> I'd like to put it back in draft. Ask me to confirm before making the change.

When the assistant asks for confirmation:

> Yes, return it to draft.

**Tools:** `publish_event`, `unpublish_event`.

**What you see:** the invitation published after your confirmation, then returned to draft after your second confirmation.
