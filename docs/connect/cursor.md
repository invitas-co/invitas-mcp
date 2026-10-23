# Connect invitas in Cursor

[English](#english) · [Español](#español)

## English

### Requirements

Cursor with Agent and MCP enabled. You need an invitas account.

### Connect

1. Merge this entry into `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (this project):

```json
{
  "mcpServers": {
    "invitas": {
      "url": "https://invitas.co/mcp"
    }
  }
}
```

2. Open **Customize**, enable invitas, and complete the OAuth sign-in when prompted.
3. In Agent chat, check that invitas tools appear under **Available Tools**.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Remove the invitas entry from that file. If you also use Cloud Agents, sign out separately on the server's Cloud row in **Customize**. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Inspect **Output → MCP Logs** for connection errors. Team policy can disable a server. Desktop and Cloud Agents maintain separate sign-ins.

## Español

### Requisitos

Cursor con Agent y MCP habilitados. Necesitas una cuenta de invitas.

### Conectar

1. Integra esta entrada en `~/.cursor/mcp.json` (todos los proyectos) o `.cursor/mcp.json` (este proyecto):

```json
{
  "mcpServers": {
    "invitas": {
      "url": "https://invitas.co/mcp"
    }
  }
}
```

2. Abre **Customize**, habilita invitas y completa el inicio de sesión OAuth cuando se solicite.
3. En el chat de Agent, comprueba las herramientas de invitas en **Available Tools**.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Elimina la entrada invitas de ese archivo. Si usas Cloud Agents, cierra también su sesión por separado en la fila Cloud del servidor en **Customize**. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Consulta errores en **Output → MCP Logs**. La política del equipo puede deshabilitar el servidor. Desktop y Cloud Agents mantienen sesiones distintas.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://cursor.com/docs/mcp
https://cursor.com/docs/cloud-agent/capabilities
-->

Sources / Fuentes: [Official documentation 1](https://cursor.com/docs/mcp) · [Official documentation 2](https://cursor.com/docs/cloud-agent/capabilities)
