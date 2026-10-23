# Connect invitas in ChatGPT

[English](#english) · [Español](#español)

## English

### Requirements

ChatGPT on the web, with permission to add custom MCP servers. Workspace policy can restrict access. You need an invitas account.

### Connect

1. Open [ChatGPT Plugins](https://chatgpt.com/plugins), select **+**, then **Add custom MCP server**.
2. Name it **invitas**, add a description, and enter `https://invitas.co/mcp` under **Connection**.
3. Choose OAuth authentication. Review the warning and continue with **Create as a plugin**. Complete the invitas browser sign-in and consent when prompted.
4. Review the discovered tools, install the custom plugin, and select it with `@` in a new chat.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Remove the custom plugin from ChatGPT Plugins. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

No add option: check your account and workspace permissions. No tools: select invitas with `@`; refresh its connection after a tool update.

## Español

### Requisitos

ChatGPT web y permiso para agregar servidores MCP personalizados. La política del espacio puede restringir el acceso. Necesitas una cuenta de invitas.

### Conectar

1. Abre [ChatGPT Plugins](https://chatgpt.com/plugins), elige **+** y **Add custom MCP server**.
2. Ponle el nombre **invitas**, agrega una descripción e introduce `https://invitas.co/mcp` en **Connection**.
3. Elige OAuth. Revisa la advertencia y continúa con **Create as a plugin**. Completa el inicio de sesión y el consentimiento de invitas en el navegador cuando se solicite.
4. Revisa las herramientas, instala el plugin personalizado y selecciónalo con `@` en un chat nuevo.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Elimina el plugin personalizado desde ChatGPT Plugins. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

No aparece la opción de agregar: revisa los permisos de tu cuenta y espacio. Sin herramientas: selecciona invitas con `@`; actualiza la conexión si cambiaron las herramientas.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://developers.openai.com/plugins/deploy/connect-chatgpt
https://developers.openai.com/plugins/build/auth
-->

Sources / Fuentes: [Official documentation 1](https://developers.openai.com/plugins/deploy/connect-chatgpt) · [Official documentation 2](https://developers.openai.com/plugins/build/auth)
