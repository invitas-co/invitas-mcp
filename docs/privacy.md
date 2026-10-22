# Datos, permisos y cómo desconectar / Data, permissions and disconnecting

## Español

### Qué ve el asistente

Tu asistente puede acceder a la información que ves como anfitrión en tu panel, dentro de los permisos que autorices. Esto incluye eventos, invitados con sus datos de contacto, enlaces de invitación, mensajes del muro, mesas y recordatorios preparados.

### A dónde viajan los datos

Al conectar tu asistente y autorizar el acceso, la información que consulta a través del conector se comparte con su proveedor: Anthropic si usas Claude, OpenAI si usas ChatGPT o el proveedor del asistente que elijas.

Consulta la [política de privacidad de invitas](https://invitas.co/privacidad) y la [lista de subprocesadores](https://invitas.co/subprocesadores) para conocer el tratamiento de datos y los proveedores involucrados.

### Qué permisos autorizas

El conector usa OAuth 2.1. Revisa la pantalla de consentimiento antes de autorizar el acceso.

| Permiso | Acceso |
| --- | --- |
| `events:read` | Consultar eventos. |
| `events:write` | Crear y actualizar eventos. |
| `guests:read` | Consultar datos de invitados. |
| `guests:write` | Agregar y actualizar invitados. |
| `seating:read` | Consultar la distribución de mesas. |
| `seating:write` | Actualizar la distribución de mesas. |

Si usas un cliente de terminal, eliges los permisos al crear tu token de acceso personal en **Mi cuenta**.

### Cómo desconectar

1. Abre [Mi cuenta](https://invitas.co/dashboard/account) en invitas.
2. Entra a **Apps conectadas**.
3. Elige la conexión y pulsa **Desconectar**.

El acceso se corta de inmediato. Los cambios que ya hayas hecho a través del asistente se conservan.

## English

### What the assistant can see

Your assistant can access the information you see as a host in your dashboard, within the permissions you authorise. This includes events, guests and their contact details, invitation links, wall messages, tables and prepared reminders.

### Where the data goes

When you connect your assistant and authorise access, information it retrieves through the connector is shared with its provider: Anthropic for Claude, OpenAI for ChatGPT or the provider of your chosen assistant.

Read the [invitas privacy policy](https://invitas.co/privacidad) and [sub-processor list](https://invitas.co/subprocesadores) for details on data handling and the providers involved.

### Permissions you authorise

The connector uses OAuth 2.1. Review the consent screen before authorising access.

| Permission | Access |
| --- | --- |
| `events:read` | Read events. |
| `events:write` | Create and update events. |
| `guests:read` | Read guest information. |
| `guests:write` | Add and update guests. |
| `seating:read` | Read table arrangements. |
| `seating:write` | Update table arrangements. |

For terminal clients, you choose the permissions when creating a personal access token in **Mi cuenta**.

### How to disconnect

1. Open [Mi cuenta](https://invitas.co/dashboard/account) in invitas.
2. Go to **Apps conectadas**.
3. Select the connection and choose **Desconectar**.

Access ends immediately. Changes you have already made through the assistant are kept.
