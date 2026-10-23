# Connect invitas in Hermes Agent (Nous Research)

[English](#english) · [Español](#español)

## English

### Requirements

A current Hermes Agent installation with MCP support, included in the standard installer. You need an invitas account.

### Connect

1. Add the custom remote server:

```sh
hermes mcp add invitas --url https://invitas.co/mcp --auth oauth
```

2. Follow the browser authorization link, sign in to invitas, and consent. If needed, run `hermes mcp login invitas`.
3. Run `hermes mcp test invitas`, then start `hermes chat`. In an existing session, use `/reload-mcp`.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `hermes mcp remove invitas`, then restart the session or use `/reload-mcp`. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Missing tools: reload MCP and check tool filters. Missing OAuth: ensure the server uses `auth: oauth`; repeat `hermes mcp login invitas`.

## Español

### Requisitos

Hermes Agent actualizado con soporte MCP, incluido en el instalador estándar. Necesitas una cuenta de invitas.

### Conectar

1. Agrega el servidor remoto personalizado:

```sh
hermes mcp add invitas --url https://invitas.co/mcp --auth oauth
```

2. Sigue el enlace de autorización, inicia sesión en invitas y autoriza. Si hace falta, ejecuta `hermes mcp login invitas`.
3. Ejecuta `hermes mcp test invitas` y abre `hermes chat`. En una sesión existente, usa `/reload-mcp`.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `hermes mcp remove invitas` y reinicia la sesión o usa `/reload-mcp`. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Sin herramientas: recarga MCP y revisa los filtros. Sin OAuth: confirma que el servidor use `auth: oauth` y repite `hermes mcp login invitas`.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://hermes-agent.nousresearch.com/docs/reference/cli-commands
https://hermes-agent.nousresearch.com/docs/reference/mcp-config-reference
https://hermes-agent.nousresearch.com/docs/user-guide/features/mcp
-->

Sources / Fuentes: [Official documentation 1](https://hermes-agent.nousresearch.com/docs/reference/cli-commands) · [Official documentation 2](https://hermes-agent.nousresearch.com/docs/reference/mcp-config-reference) · [Official documentation 3](https://hermes-agent.nousresearch.com/docs/user-guide/features/mcp)
