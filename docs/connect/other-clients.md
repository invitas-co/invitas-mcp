# Other MCP clients and terminal / Otros clientes MCP y terminal

[English](#english) · [Español](#español)

## English

### MCP clients

You need an invitas account and a client that supports Streamable HTTP. The connector is available at `https://invitas.co/mcp` over stateless Streamable HTTP. Start with a [client guide](../../README.md#connect-it).

Configure a remote HTTP server with that URL. If your client supports OAuth 2.1 with PKCE and dynamic registration, start its authentication action, open the browser, and sign in to invitas. Review consent. These are the public discovery documents:

- [Authorisation server](https://invitas.co/.well-known/oauth-authorization-server)
- [MCP protected resource](https://invitas.co/.well-known/oauth-protected-resource/mcp)

### Personal token alternative

If the client lacks OAuth but supports bearer headers:

1. Open **Mi cuenta** in invitas.
2. Create a personal access token and choose the permissions you need.
3. Configure your terminal MCP client with `https://invitas.co/mcp` and the `Authorization: Bearer <token>` header, replacing `<token>` with your personal token.

### Verify, disconnect, and troubleshoot

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check the tool call and its result, including an empty list.

Remove the server from your client and revoke its grant in [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. If you used a personal token, revoke it in Mi cuenta too.

A 401 requires authentication. A client without remote OAuth or bearer-header support cannot use this connection directly. Choose a compatible client guide; keep credentials out of chat.

See [Data and permissions](../privacy.md) for permission and data-sharing details. To integrate the REST API directly, use the [developer documentation](https://invitas.co/developers) and the [OpenAPI specification](https://invitas.co/api/openapi.json).

## Español

### Clientes MCP

Necesitas una cuenta de invitas y un cliente compatible con Streamable HTTP. El conector está disponible en `https://invitas.co/mcp`, sin estado. Elige primero una [guía por cliente](../../README.es.md#cómo-conectarlo).

Configura un servidor HTTP remoto con esa URL. Si tu cliente admite OAuth 2.1 con PKCE y registro dinámico, inicia su opción de autenticación, abre el navegador e inicia sesión en invitas. Revisa el consentimiento. Estos son los documentos públicos de descubrimiento:

- [Servidor de autorización](https://invitas.co/.well-known/oauth-authorization-server)
- [Recurso protegido MCP](https://invitas.co/.well-known/oauth-protected-resource/mcp)

### Alternativa con token personal

Si el cliente no admite OAuth pero sí cabeceras bearer:

1. Abre **Mi cuenta** en invitas.
2. Crea un token de acceso personal y elige los permisos que necesitas.
3. Configura tu cliente MCP de terminal con `https://invitas.co/mcp` y la cabecera `Authorization: Bearer <token>`, sustituyendo `<token>` por tu token personal.

### Verificar, desconectar y resolver problemas

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba la llamada a herramienta y su resultado, incluso si la lista está vacía.

Elimina el servidor del cliente y revoca su permiso en [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Si usaste un token personal, revócalo también en Mi cuenta.

Un 401 requiere autenticación. Si no admite OAuth remoto ni cabeceras bearer, el cliente no puede usar esta conexión directamente. Usa una guía compatible; no pegues credenciales en el chat.

Consulta los permisos y el uso de datos en [Datos y permisos](../privacy.md). Para integrar directamente la API REST, visita la [documentación para desarrolladores](https://invitas.co/developers) y la [especificación OpenAPI](https://invitas.co/api/openapi.json).


<!-- Official source consulted: 2026-10-22 (America/Bogota).
https://modelcontextprotocol.io/specification/2025-06-18/basic/authorization
-->

Source / Fuente: [MCP authorization specification](https://modelcontextprotocol.io/specification/2025-06-18/basic/authorization).
