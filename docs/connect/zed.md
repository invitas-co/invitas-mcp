# Connect invitas in Zed

[English](#english) · [Español](#español)

## English

### Requirements

A current Zed release and a configured model for Zed Agent. You need an invitas account.

### Connect

1. Open **Settings → AI → MCP Servers → Add Server → Add Remote Server**.
2. Name it `invitas` and enter `https://invitas.co/mcp`. Leave the Authorization header unset so Zed can use OAuth.
3. Follow Zed's authentication prompt, sign in to invitas in the browser, and consent.
4. Check that the server indicator is green, then use the Agent Panel.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Remove `context_servers.invitas` from your Zed settings file using **zed: open settings file**. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

A non-green indicator shows connection details on hover. Check tool permissions in the active agent profile. Terminal Threads use the terminal client's own configuration.

## Español

### Requisitos

Zed actualizado y un modelo configurado para Zed Agent. Necesitas una cuenta de invitas.

### Conectar

1. Abre **Settings → AI → MCP Servers → Add Server → Add Remote Server**.
2. Ponle el nombre `invitas` e introduce `https://invitas.co/mcp`. Deja vacía la cabecera Authorization para usar OAuth.
3. Sigue la solicitud de autenticación, inicia sesión en invitas desde el navegador y autoriza.
4. Comprueba que el indicador del servidor esté verde y usa el Agent Panel.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Elimina `context_servers.invitas` del archivo de configuración de Zed con **zed: open settings file**. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Si el indicador no está verde, pasa el cursor para ver detalles. Revisa los permisos del perfil de agente activo. Terminal Threads usa la configuración del cliente de terminal.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://zed.dev/docs/ai/mcp
https://zed.dev/docs/ai/agent-panel
-->

Sources / Fuentes: [Official documentation 1](https://zed.dev/docs/ai/mcp) · [Official documentation 2](https://zed.dev/docs/ai/agent-panel)
