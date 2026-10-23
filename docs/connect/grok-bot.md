# Connect invitas in Grok Bot for teams / Grok Bot para equipos

[English](#english) · [Español](#español)

## English

### Requirements

Team Bot access and permission as the Bot owner or manager. Your team must allow the MCP server. You need an invitas account.

### Connect

1. Open the Team Bot in the desktop app. In its info pane, open **Setup → Plugins**.
2. Choose **Add plugins → Add custom**, select **Remote HTTPS**, and enter `https://invitas.co/mcp`. Use OAuth account sign-in.
3. Each teammate completes their own invitas browser sign-in when prompted.
4. Ask the Bot to use invitas in that teammate's chat.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

The owner or manager removes invitas from the Team Bot's Plugins card; each user should also revoke their invitas grant. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Disabled by team admin: ask the administrator to allow the server. An owner's OAuth session does not connect other teammates.

## Español

### Requisitos

Acceso a Team Bots y permiso como propietario o gestor del Bot. El equipo debe permitir el servidor MCP. Necesitas una cuenta de invitas.

### Conectar

1. Abre el Team Bot en la app de escritorio. En su panel de información, abre **Setup → Plugins**.
2. Elige **Add plugins → Add custom**, selecciona **Remote HTTPS** e introduce `https://invitas.co/mcp`. Usa el acceso a cuenta con OAuth.
3. Cada miembro completa su propio inicio de sesión en invitas desde el navegador cuando se solicita.
4. Pide al Bot que use invitas en el chat de ese miembro.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

El propietario o gestor elimina invitas desde la tarjeta Plugins del Team Bot; cada usuario debe revocar también su permiso en invitas. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Disabled by team admin: pide al administrador que permita el servidor. La sesión OAuth del propietario no conecta a los demás miembros.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://docs.x.ai/grok-bot/team-bots
https://docs.x.ai/grok-bot/teams-and-enterprises
https://forum.cursor.com/t/how-do-i-share-a-custom-mcp-that-one-of-my-bots-has-built-with-the-rest-of-my-team/173538
-->

Sources / Fuentes: [Official documentation 1](https://docs.x.ai/grok-bot/team-bots) · [Official documentation 2](https://docs.x.ai/grok-bot/teams-and-enterprises) · [Official documentation 3](https://forum.cursor.com/t/how-do-i-share-a-custom-mcp-that-one-of-my-bots-has-built-with-the-rest-of-my-team/173538)
