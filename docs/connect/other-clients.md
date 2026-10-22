# Otros clientes MCP y terminal / Other MCP clients and terminal

## Español

### Clientes MCP

El conector está disponible en `https://invitas.co/mcp` mediante Streamable HTTP, sin estado. Para las opciones de conexión con Perplexity, Gemini y otros asistentes, consulta la [guía de invitas](https://invitas.co/asistentes).

Los clientes compatibles con OAuth 2.1 pueden usar el registro dinámico de clientes y estos documentos públicos de descubrimiento:

- [Servidor de autorización](https://invitas.co/.well-known/oauth-authorization-server)
- [Recurso protegido MCP](https://invitas.co/.well-known/oauth-protected-resource/mcp)

### Clientes de terminal

1. Abre **Mi cuenta** en invitas.
2. Crea un token de acceso personal y elige los permisos que necesitas.
3. Configura tu cliente MCP de terminal con `https://invitas.co/mcp` y la cabecera `Authorization: Bearer <token>`, sustituyendo `<token>` por tu token personal.

Consulta los permisos y el uso de datos en [Datos y permisos](../privacy.md). Para integrar directamente la API REST, visita la [documentación para desarrolladores](https://invitas.co/developers) y la [especificación OpenAPI](https://invitas.co/api/openapi.json).

## English

### MCP clients

The connector is available at `https://invitas.co/mcp` over stateless Streamable HTTP. For connection options with Perplexity, Gemini and other assistants, see the [invitas guide](https://invitas.co/asistentes).

Clients that support OAuth 2.1 can use dynamic client registration and these public discovery documents:

- [Authorisation server](https://invitas.co/.well-known/oauth-authorization-server)
- [MCP protected resource](https://invitas.co/.well-known/oauth-protected-resource/mcp)

### Terminal clients

1. Open **Mi cuenta** in invitas.
2. Create a personal access token and choose the permissions you need.
3. Configure your terminal MCP client with `https://invitas.co/mcp` and the `Authorization: Bearer <token>` header, replacing `<token>` with your personal token.

See [Data and permissions](../privacy.md) for permission and data-sharing details. To integrate the REST API directly, use the [developer documentation](https://invitas.co/developers) and the [OpenAPI specification](https://invitas.co/api/openapi.json).
