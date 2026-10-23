# Connect invitas in OpenClaw

[English](#english) · [Español](#español)

## English

### Requirements

A current OpenClaw installation and permission to edit MCP settings. This setup authorises the operator account; use it only with trusted users of that agent. You need an invitas account.

### Connect

1. Save an OAuth HTTP server:

```sh
openclaw mcp set invitas '{"url":"https://invitas.co/mcp","transport":"streamable-http","auth":"oauth"}'
```

2. Run `openclaw mcp login invitas`. Open the printed URL, sign in to invitas, and consent.
3. Run `openclaw mcp doctor invitas --probe`, then `openclaw mcp reload` to refresh tools.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `openclaw mcp logout invitas`, then `openclaw mcp unset invitas` and reload MCP. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Use `streamable-http` explicitly. A config-only status does not prove connectivity; use `--probe`. Shared credentials are operator-managed; per-requester OAuth requires additional gateway configuration.

## Español

### Requisitos

OpenClaw actualizado y permiso para editar MCP. Esta configuración autoriza la cuenta del operador; úsala solo con usuarios de confianza de ese agente. Necesitas una cuenta de invitas.

### Conectar

1. Guarda un servidor HTTP con OAuth:

```sh
openclaw mcp set invitas '{"url":"https://invitas.co/mcp","transport":"streamable-http","auth":"oauth"}'
```

2. Ejecuta `openclaw mcp login invitas`. Abre la URL impresa, inicia sesión en invitas y autoriza.
3. Ejecuta `openclaw mcp doctor invitas --probe` y después `openclaw mcp reload` para actualizar las herramientas.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `openclaw mcp logout invitas`, después `openclaw mcp unset invitas` y recarga MCP. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Indica `streamable-http` explícitamente. El estado de configuración no demuestra conectividad; usa `--probe`. El operador gestiona las credenciales compartidas; OAuth por usuario requiere configuración adicional.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://docs.openclaw.ai/cli/mcp/transports
https://docs.openclaw.ai/cli/mcp/registry
https://docs.openclaw.ai/tools/mcp
-->

Sources / Fuentes: [Official documentation 1](https://docs.openclaw.ai/cli/mcp/transports) · [Official documentation 2](https://docs.openclaw.ai/cli/mcp/registry) · [Official documentation 3](https://docs.openclaw.ai/tools/mcp)
