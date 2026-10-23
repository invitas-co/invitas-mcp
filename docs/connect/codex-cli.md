# Connect invitas in Codex CLI

[English](#english) · [Español](#español)

## English

### Requirements

A current Codex CLI installation. You need an invitas account.

### Connect

1. Register the HTTP server:

```sh
codex mcp add invitas --url https://invitas.co/mcp
```

2. The command can start OAuth automatically. Open the printed URL, sign in to invitas, and consent. If it does not start, run `codex mcp login invitas`.
3. Check `codex mcp list`; start `codex` and inspect `/mcp`.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Run `codex mcp logout invitas`, then `codex mcp remove invitas`. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

No tools: inspect `/mcp` and repeat login if required. Keep the terminal running until the browser callback completes.

## Español

### Requisitos

Codex CLI actualizado. Necesitas una cuenta de invitas.

### Conectar

1. Registra el servidor HTTP:

```sh
codex mcp add invitas --url https://invitas.co/mcp
```

2. El comando puede iniciar OAuth automáticamente. Abre la URL que imprime, inicia sesión en invitas y autoriza. Si no se inicia, ejecuta `codex mcp login invitas`.
3. Revisa `codex mcp list`; abre `codex` y consulta `/mcp`.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Ejecuta `codex mcp logout invitas` y después `codex mcp remove invitas`. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Sin herramientas: consulta `/mcp` y repite el login si hace falta. Mantén abierta la terminal hasta completar el retorno del navegador.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://learn.chatgpt.com/docs/extend/mcp?surface=cli
https://developers.openai.com/learn/docs-mcp
-->

Sources / Fuentes: [Official documentation 1](https://learn.chatgpt.com/docs/extend/mcp?surface=cli) · [Official documentation 2](https://developers.openai.com/learn/docs-mcp)
