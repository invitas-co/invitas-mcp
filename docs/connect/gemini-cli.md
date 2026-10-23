# Connect invitas in Gemini CLI

[English](#english) · [Español](#español)

## English

### Requirements

A current Gemini CLI installation, provider setup completed, and a local browser. You need an invitas account.

### Connect

1. From your project, add the HTTP server:

```sh
gemini mcp add --transport http invitas https://invitas.co/mcp
```

2. Start `gemini` in that project and trust the folder if prompted.
3. Run `/mcp auth invitas`; complete invitas sign-in and consent in the browser. Run `/mcp list` to check the tools.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

From the same project, run `gemini mcp remove invitas`. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Authentication requires a browser that can reach the local callback. An untrusted project can hide its MCP configuration. Use `/mcp list` for diagnostics.

## Español

### Requisitos

Gemini CLI actualizado, acceso al proveedor configurado y navegador local. Necesitas una cuenta de invitas.

### Conectar

1. Desde tu proyecto, agrega el servidor HTTP:

```sh
gemini mcp add --transport http invitas https://invitas.co/mcp
```

2. Abre `gemini` en ese proyecto y confirma la confianza en la carpeta si se solicita.
3. Ejecuta `/mcp auth invitas`; inicia sesión y autoriza en invitas desde el navegador. Consulta las herramientas con `/mcp list`.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Desde el mismo proyecto, ejecuta `gemini mcp remove invitas`. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

La autenticación requiere un navegador que pueda devolver el control al cliente local. Un proyecto sin confianza puede ocultar su configuración MCP. Consulta `/mcp list` para diagnosticar.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://geminicli.com/docs/tools/mcp-server/
https://geminicli.com/docs/get-started/authentication/
-->

Sources / Fuentes: [Official documentation 1](https://geminicli.com/docs/tools/mcp-server/) · [Official documentation 2](https://geminicli.com/docs/get-started/authentication/)
