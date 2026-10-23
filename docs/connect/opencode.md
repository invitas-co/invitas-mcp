# Connect invitas in OpenCode

[English](#english) · [Español](#español)

## English

### Requirements

OpenCode 1.x or V2. Check your version with `opencode --version`; their configuration schemas differ. You need an invitas account.

### Connect

**OpenCode 1.x:** merge this entry into your project's `opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "invitas": {
      "type": "remote",
      "url": "https://invitas.co/mcp"
    }
  }
}
```

**OpenCode V2:** from your project, run `opencode mcp add invitas --url https://invitas.co/mcp`. It writes the V2 entry under `mcp.servers`.

**Both versions:** run `opencode mcp auth invitas`, sign in and consent in the browser. Check `opencode mcp list`, then start `opencode` in that project.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `opencode mcp logout invitas`, then remove `mcp.invitas` (1.x) or `mcp.servers.invitas` (V2) from the configuration. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

In 1.x, use `opencode mcp debug invitas` if no authorization page appears. In V2, inspect `/mcps`. Keep OAuth enabled and use the schema for your version.

## Español

### Requisitos

OpenCode 1.x o V2. Consulta la versión con `opencode --version`; sus esquemas de configuración son distintos. Necesitas una cuenta de invitas.

### Conectar

**OpenCode 1.x:** integra esta entrada en el `opencode.json` de tu proyecto:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "invitas": {
      "type": "remote",
      "url": "https://invitas.co/mcp"
    }
  }
}
```

**OpenCode V2:** desde tu proyecto, ejecuta `opencode mcp add invitas --url https://invitas.co/mcp`. Guarda la entrada V2 bajo `mcp.servers`.

**Ambas versiones:** ejecuta `opencode mcp auth invitas`, inicia sesión y autoriza desde el navegador. Revisa `opencode mcp list` y abre `opencode` en ese proyecto.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `opencode mcp logout invitas` y elimina `mcp.invitas` (1.x) o `mcp.servers.invitas` (V2) de la configuración. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

En 1.x, usa `opencode mcp debug invitas` si no aparece la autorización. En V2, consulta `/mcps`. Mantén OAuth habilitado y usa el esquema de tu versión.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://opencode.ai/docs/mcp-servers/
https://dev.opencode.ai/v2/docs/mcp-servers/
-->

Sources / Fuentes: [Official documentation 1](https://opencode.ai/docs/mcp-servers/) · [Official documentation 2](https://dev.opencode.ai/v2/docs/mcp-servers/)
