# Connect invitas in Muse Code (Meta)

[English](#english) · [Español](#español)

## English

### Requirements

Muse Code with custom MCP support. This guide covers the coding client. You need an invitas account.

### Connect

1. Merge this entry into `~/.config/muse/settings.json`:

```json
{
  "mcp_servers": {
    "invitas": {
      "transport": "streamable_http",
      "url": "https://invitas.co/mcp",
      "enabled": true,
      "mode": "optional"
    }
  }
}
```

2. Run `muse mcp login invitas`; sign in to invitas and consent in the browser.
3. Start `muse` and inspect `/mcp` for the server and tools.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `muse mcp logout invitas`, then remove `mcp_servers.invitas` from settings. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Missing login command: update Muse Code. Keep dynamic client registration enabled. The optional mode lets the session start while the server needs sign-in.

## Español

### Requisitos

Muse Code con soporte para MCP personalizados. Esta guía corresponde al cliente de código. Necesitas una cuenta de invitas.

### Conectar

1. Integra esta entrada en `~/.config/muse/settings.json`:

```json
{
  "mcp_servers": {
    "invitas": {
      "transport": "streamable_http",
      "url": "https://invitas.co/mcp",
      "enabled": true,
      "mode": "optional"
    }
  }
}
```

2. Ejecuta `muse mcp login invitas`; inicia sesión en invitas y autoriza desde el navegador.
3. Abre `muse` y consulta el servidor y sus herramientas con `/mcp`.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `muse mcp logout invitas` y elimina `mcp_servers.invitas` de la configuración. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Sin comando de login: actualiza Muse Code. Mantén habilitado el registro dinámico de clientes. El modo optional permite abrir la sesión mientras falta autenticar el servidor.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://dev.meta.ai/docs/muse-code/extending
https://dev.meta.ai/docs/muse-code/configuration
-->

Sources / Fuentes: [Official documentation 1](https://dev.meta.ai/docs/muse-code/extending) · [Official documentation 2](https://dev.meta.ai/docs/muse-code/configuration)
