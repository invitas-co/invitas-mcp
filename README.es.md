# Conector MCP de invitas

[English](README.md)

![Protocolo del Conector MCP de invitas](docs/images/mcp-terminal-inspector.webp)

Servidor oficial de Model Context Protocol (MCP) para [invitas.co](https://invitas.co). Crea, personaliza y administra tus invitaciones, listas de invitados, confirmaciones de asistencia y distribución de mesas directamente desde Claude, ChatGPT, Cursor y cualquier asistente compatible con MCP.

**Dirección del conector:** `https://invitas.co/mcp` (Streamable HTTP / JSON-RPC 2.0)

---

## Arquitectura y Flujo de Interacción

El conector expone 31 herramientas nativas mediante Streamable HTTP y JSON-RPC 2.0, autenticando solicitudes con OAuth 2.1 (PKCE) o Tokens de Acceso Personal (PAT).

```mermaid
sequenceDiagram
    autonumber
    actor User as Anfitrión / Desarrollador
    participant Client as Cliente MCP (Claude / ChatGPT / Cursor)
    participant Connector as Conector MCP invitas (https://invitas.co/mcp)
    participant App as API Central de invitas.co

    User->>Client: "¿Cuántos invitados han confirmado para mi evento?"
    Client->>Connector: POST /mcp (tools/call: list_guests)
    Connector->>App: GET /api/v1/events/{id}/guests (Bearer Token)
    App-->>Connector: 200 OK (datos de invitados y confirmaciones)
    Connector-->>Client: 200 OK (resultado JSON-RPC para el modelo)
    Client-->>User: "Tienes 26 invitados confirmados de un total de 41 convocados."
```

---

## Categorías de Herramientas (31 Herramientas)

Todas las herramientas se catalogan y sincronizan desde la especificación central de la API. Consulta el [Catálogo completo de herramientas](docs/tools.md) para esquemas y parámetros detallados.

| Categoría | Herramientas Disponibles | Permisos Requeridos |
|---|---|---|
| **Búsqueda y Guía** | `guide`, `search`, `fetch` | `events:read` |
| **Eventos y Plantillas** | `list_templates`, `list_events`, `get_event`, `create_event`, `update_event`, `publish_event`, `unpublish_event`, `duplicate_event`, `export_event` | `events:read`, `events:write` |
| **Medios y Secciones** | `add_event_image`, `upsert_custom_section`, `set_custom_fields` | `events:read`, `events:write` |
| **Invitados y RSVPs** | `list_guests`, `get_guest`, `add_guest`, `update_guest`, `remove_guest`, `import_guests`, `export_guests` | `guests:read`, `guests:write` |
| **Mesas y Asientos** | `get_seating_chart`, `update_seating_chart`, `assign_guest_table`, `unassign_guest_table` | `seating:read`, `seating:write` |
| **Comunicaciones y Muro** | `list_wall_messages`, `moderate_wall_message`, `prepare_reminder`, `get_event_statistics` | `events:read`, `guests:read` |

---

## Ejemplos de Configuración en Clientes

### Claude Desktop (`claude_desktop_config.json`)

```json
{
  "mcpServers": {
    "invitas": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-sse",
        "https://invitas.co/mcp"
      ]
    }
  }
}
```

### Cursor (`.cursor/mcp.json`)

```json
{
  "mcpServers": {
    "invitas": {
      "url": "https://invitas.co/mcp"
    }
  }
}
```

### Solicitud HTTP Directa

```sh
# Descubrir herramientas disponibles
curl -X POST https://invitas.co/mcp \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer TU_TOKEN_DE_ACCESO_PERSONAL" \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "tools/list"}'
```

---

## Asistentes Compatibles

Guías de conexión paso a paso para los principales entornos:

- [ChatGPT](docs/connect/chatgpt.md#español)
- [Claude app y web](docs/connect/claude.md#español)
- [Claude Code](docs/connect/claude-code.md#español)
- [Codex CLI](docs/connect/codex-cli.md#español)
- [Gemini CLI](docs/connect/gemini-cli.md#español)
- [Cursor](docs/connect/cursor.md#español)
- [VS Code (GitHub Copilot)](docs/connect/vscode.md#español)
- [OpenCode](docs/connect/opencode.md#español)
- [Hermes Agent (Nous Research)](docs/connect/hermes-agent.md#español)
- [OpenClaw](docs/connect/openclaw.md#español)
- [Grok (grok.com)](docs/connect/grok.md#español)
- [Grok Build](docs/connect/grok-build.md#español)
- [Grok Bot para equipos](docs/connect/grok-bot.md#español)
- [Agente de código Pi](docs/connect/pi.md#español)
- [Windsurf / Cascade](docs/connect/windsurf.md#español)
- [Zed](docs/connect/zed.md#español)
- [Muse Code (Meta)](docs/connect/muse-code.md#español)
- [Otros clientes MCP y terminal](docs/connect/other-clients.md#español)

---

## Inicio de Sesión y Permisos

El conector usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Inicia sesión en invitas cuando se te solicite y revisa la pantalla de consentimiento antes de autorizar a tu asistente.

| Permiso | Acceso |
| --- | --- |
| `events:read` | Consultar eventos. |
| `events:write` | Crear y actualizar eventos. |
| `guests:read` | Consultar datos de invitados. |
| `guests:write` | Agregar y actualizar invitados. |
| `seating:read` | Consultar la distribución de mesas. |
| `seating:write` | Actualizar la distribución de mesas. |

Los clientes de terminal compatibles con OAuth pueden usar el inicio de sesión en el navegador siguiendo las guías anteriores. Para clientes que admitan cabeceras bearer, crea un token de acceso personal en **Mi cuenta**, elige sus permisos y envíalo en la cabecera `Authorization: Bearer <token>`. Consulta los detalles en [Otros clientes MCP y terminal](docs/connect/other-clients.md#español).

---

## Qué Ve el Asistente y Cómo Desconectarlo

Dentro de los permisos que autorices, tu asistente puede acceder a la información del evento que ves en tu panel, incluidos los datos de contacto de invitados, enlaces de invitación, mensajes del muro, mesas y recordatorios preparados. Al conectar y autorizar el acceso, esa información puede compartirse con el proveedor de tu asistente, como Anthropic con Claude u OpenAI con ChatGPT. Para cortar el acceso de inmediato, entra a [Mi cuenta](https://invitas.co/dashboard/account), elige **Apps conectadas** y pulsa **Desconectar**; los cambios ya realizados se conservan. Consulta los detalles en [Datos y permisos](docs/privacy.md).

---

## Ejemplos

Consulta los [ejemplos de conversación](examples/conversations.md) para ver qué puedes pedir, qué herramientas intervienen y qué resultado esperar.

---

## Enlaces

- [Asistentes](https://invitas.co/asistentes)
- [Desarrolladores y API REST](https://invitas.co/developers) · [Especificación OpenAPI](https://invitas.co/api/openapi.json)
- [Privacidad](https://invitas.co/privacidad) · [Subprocesadores](https://invitas.co/subprocesadores) · [Términos](https://invitas.co/terminos)
- [Ayuda](https://invitas.co/ayuda) · Soporte: hola@invitas.co

---

## Desarrollo del Repositorio

Este repositorio contiene la documentación pública y el catálogo generado de herramientas; el servidor alojado del conector corre dentro de la aplicación principal de invitas. Con Node.js 22 instalado, ejecuta `npm run check` para verificar que los archivos generados coincidan con el origen. Ejecuta `npm run catalog` tras modificar `docs/catalog.source.json`. Consulta [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Licencia

Documentación: [CC BY 4.0](LICENSE).
