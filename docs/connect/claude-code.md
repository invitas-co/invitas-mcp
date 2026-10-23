# Connect invitas in Claude Code

[English](#english) · [Español](#español)

## English

### Requirements

A current Claude Code installation and an interactive terminal. You need an invitas account.

### Connect

1. Add a user-scoped HTTP server:

```sh
claude mcp add --transport http --scope user invitas https://invitas.co/mcp
```

2. Run `claude mcp login invitas`, then sign in and consent in the browser. For a headless terminal, use `claude mcp login invitas --no-browser` and follow its redirect-paste instructions.
3. Start `claude` and inspect `/mcp`.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `claude mcp logout invitas`, then `claude mcp remove --scope user invitas`. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Needs authentication: repeat login. A non-interactive terminal cannot accept the pasted redirect; use an interactive terminal. Check configuration with `claude mcp get invitas`.

## Español

### Requisitos

Claude Code actualizado y una terminal interactiva. Necesitas una cuenta de invitas.

### Conectar

1. Agrega el servidor HTTP para tu usuario:

```sh
claude mcp add --transport http --scope user invitas https://invitas.co/mcp
```

2. Ejecuta `claude mcp login invitas` e inicia sesión y autoriza en el navegador. Sin navegador local, usa `claude mcp login invitas --no-browser` y sigue las instrucciones para pegar la redirección.
3. Abre `claude` y consulta `/mcp`.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `claude mcp logout invitas` y después `claude mcp remove --scope user invitas`. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Needs authentication: repite el login. Una terminal no interactiva no puede recibir la redirección pegada; usa una interactiva. Consulta la configuración con `claude mcp get invitas`.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://code.claude.com/docs/en/mcp
-->

Sources / Fuentes: [Official documentation 1](https://code.claude.com/docs/en/mcp)
