# Connect invitas in Grok Build

[English](#english) · [Español](#español)

## English

### Requirements

A current Grok Build CLI with its provider sign-in already configured. You need an invitas account.

### Connect

1. Register the server:

```sh
grok mcp add --transport http invitas https://invitas.co/mcp
```

2. Start `grok` and open `/mcps`. Select invitas and press `i` to authenticate. Sign in to invitas and consent in the browser.
3. Check `grok mcp doctor invitas` after authorization.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `grok mcp remove invitas`. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

A 401 before sign-in is expected: `doctor` checks connectivity but does not replace the `/mcps` login. After editing configuration, press `r` in `/mcps`.

## Español

### Requisitos

Grok Build CLI actualizado con su acceso al proveedor ya configurado. Necesitas una cuenta de invitas.

### Conectar

1. Registra el servidor:

```sh
grok mcp add --transport http invitas https://invitas.co/mcp
```

2. Abre `grok` y ejecuta `/mcps`. Selecciona invitas y pulsa `i` para autenticar. Inicia sesión en invitas y autoriza desde el navegador.
3. Después de autorizar, ejecuta `grok mcp doctor invitas`.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `grok mcp remove invitas`. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Un 401 antes del login es normal: `doctor` comprueba la conexión, pero no sustituye el acceso desde `/mcps`. Después de editar la configuración, pulsa `r` en `/mcps`.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://docs.x.ai/build/features/mcp-servers
https://docs.x.ai/build/cli/reference
-->

Sources / Fuentes: [Official documentation 1](https://docs.x.ai/build/features/mcp-servers) · [Official documentation 2](https://docs.x.ai/build/cli/reference)
