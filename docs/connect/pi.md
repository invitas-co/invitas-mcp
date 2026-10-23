# Connect invitas in Pi coding agent / Agente de código Pi

[English](#english) · [Español](#español)

## English

### Requirements

A current Pi release with built-in `pi mcp` commands. Older releases without those commands do not support this setup. You need an invitas account.

### Connect

1. Add the HTTP server and start browser authorization:

```sh
pi mcp add invitas --url https://invitas.co/mcp
pi mcp login invitas
```

2. Sign in to invitas and consent in the browser.
3. Run `pi mcp list`, start `pi`, and inspect `/mcp`. Use `/reload` if the session was already open.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `pi mcp logout invitas`, then `pi mcp remove invitas`. Reload an open session. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Unknown `mcp` command: update Pi; older documentation describing no MCP support does not apply to current releases. Use HTTP, since Pi does not support legacy SSE.

## Español

### Requisitos

Una versión actual de Pi con los comandos integrados `pi mcp`. Las versiones antiguas sin esos comandos no admiten esta configuración. Necesitas una cuenta de invitas.

### Conectar

1. Agrega el servidor HTTP e inicia la autorización:

```sh
pi mcp add invitas --url https://invitas.co/mcp
pi mcp login invitas
```

2. Inicia sesión en invitas y autoriza desde el navegador.
3. Ejecuta `pi mcp list`, abre `pi` y consulta `/mcp`. Usa `/reload` si la sesión ya estaba abierta.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `pi mcp logout invitas` y después `pi mcp remove invitas`. Recarga la sesión si está abierta. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Comando `mcp` desconocido: actualiza Pi; la documentación antigua que indica ausencia de MCP no corresponde a las versiones actuales. Usa HTTP, porque Pi no admite SSE antiguo.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/mcp.md
https://github.com/earendil-works/pi/releases
-->

Sources / Fuentes: [Official documentation 1](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/mcp.md) · [Official documentation 2](https://github.com/earendil-works/pi/releases)
