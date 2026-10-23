# Conector MCP de invitas

[English](README.md)

Crea y gestiona tu invitación y tus invitados de invitas desde ChatGPT, Claude y otros asistentes. El conector sirve tanto a anfitriones que quieren organizar su evento conversando como a desarrolladores que conectan su propio cliente MCP.

MCP (Model Context Protocol) es un estándar que permite a los asistentes de IA usar herramientas y datos de servicios como invitas.

**Dirección del conector:** `https://invitas.co/mcp`

## Qué puedes hacer

- Crear una invitación con una plantilla y editar sus textos.
- Compartir con cada invitado su enlace personal.
- Organizar tus invitados, registrar confirmaciones de asistencia y distribuir las mesas.
- Preparar recordatorios para compartir con tus invitados.

La lista completa de herramientas se genera desde el catálogo del producto: [Catálogo de herramientas](docs/tools.md).

## Cómo conectarlo

Elige tu asistente, conéctalo a invitas y revisa los permisos antes de autorizar el acceso. El conector está incluido en todos los planes de invitas, también en el gratuito. Las funciones y los límites de tu evento corresponden al plan que tenga.

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

## Inicio de sesión y permisos

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

## Qué ve el asistente y cómo desconectarlo

Dentro de los permisos que autorices, tu asistente puede acceder a la información del evento que ves en tu panel, incluidos los datos de contacto de invitados, enlaces de invitación, mensajes del muro, mesas y recordatorios preparados. Al conectar y autorizar el acceso, esa información puede compartirse con el proveedor de tu asistente, como Anthropic con Claude u OpenAI con ChatGPT. Para cortar el acceso de inmediato, entra a [Mi cuenta](https://invitas.co/dashboard/account), elige **Apps conectadas** y pulsa **Desconectar**; los cambios ya realizados se conservan. Consulta los detalles en [Datos y permisos](docs/privacy.md).

## Ejemplos

Consulta los [ejemplos de conversación](examples/conversations.md) para ver qué puedes pedir, qué herramientas intervienen y qué resultado esperar.

## Enlaces

- [Asistentes](https://invitas.co/asistentes)
- [Desarrolladores y API REST](https://invitas.co/developers) · [Especificación OpenAPI](https://invitas.co/api/openapi.json)
- [Privacidad](https://invitas.co/privacidad) · [Subprocesadores](https://invitas.co/subprocesadores) · [Términos](https://invitas.co/terminos)
- [Ayuda](https://invitas.co/ayuda) · Soporte: hola@invitas.co

## Licencia

Documentación: [CC BY 4.0](LICENSE).
