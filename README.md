# invitas MCP connector

[Español](README.es.md)

Create and manage your invitas invitation and guests from ChatGPT, Claude and other assistants. This connector is for hosts who want to organise their event through conversation and developers connecting their own MCP client.

MCP (Model Context Protocol) is a standard that lets AI assistants use tools and data from services such as invitas.

**Connector URL:** `https://invitas.co/mcp`

## What you can do

- Create an invitation from a template and edit its text.
- Share each guest's personal link with them.
- Organise your guest list, record attendance confirmations and arrange tables.
- Prepare reminders to share with your guests.

The full tool list is generated from the product catalogue: [Tool catalogue](docs/tools.md).

## Connect it

Choose your assistant below, connect it to invitas and review the permissions before authorising access. The connector is included in every invitas plan, including the free plan. Your event's features and limits follow its plan.

- [ChatGPT](docs/connect/chatgpt.md)
- [Claude app and web](docs/connect/claude.md)
- [Claude Code](docs/connect/claude-code.md)
- [Codex CLI](docs/connect/codex-cli.md)
- [Gemini CLI](docs/connect/gemini-cli.md)
- [Cursor](docs/connect/cursor.md)
- [VS Code (GitHub Copilot)](docs/connect/vscode.md)
- [OpenCode](docs/connect/opencode.md)
- [Hermes Agent (Nous Research)](docs/connect/hermes-agent.md)
- [OpenClaw](docs/connect/openclaw.md)
- [Grok (grok.com)](docs/connect/grok.md)
- [Grok Build](docs/connect/grok-build.md)
- [Grok Bot for teams](docs/connect/grok-bot.md)
- [Pi coding agent](docs/connect/pi.md)
- [Windsurf / Cascade](docs/connect/windsurf.md)
- [Zed](docs/connect/zed.md)
- [Muse Code (Meta)](docs/connect/muse-code.md)
- [Other MCP clients and terminal](docs/connect/other-clients.md)

## Sign-in and permissions

The connector uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Sign in to invitas when prompted, then review the consent screen before authorising your assistant.

| Permission | Access |
| --- | --- |
| `events:read` | Read events. |
| `events:write` | Create and update events. |
| `guests:read` | Read guest information. |
| `guests:write` | Add and update guests. |
| `seating:read` | Read table arrangements. |
| `seating:write` | Update table arrangements. |

Terminal clients that support OAuth can use browser sign-in through the guides above. For clients that support bearer headers instead, create a personal access token in **Mi cuenta**, choose its permissions and send it in the `Authorization: Bearer <token>` header. See [Other MCP clients and terminal](docs/connect/other-clients.md) for connection details.

## What the assistant sees, and how to disconnect

Within the permissions you authorise, your assistant can access the event information you see in your dashboard, including guest contact details, invitation links, wall messages, tables and prepared reminders. When you connect and authorise access, that information can be shared with your assistant's provider, such as Anthropic for Claude or OpenAI for ChatGPT. To end access immediately, open [Mi cuenta](https://invitas.co/dashboard/account), select **Apps conectadas**, then **Desconectar**; changes already made are kept. See [Data and permissions](docs/privacy.md) for details.

## Examples

See [example conversations](examples/conversations.md) for requests you can make, the tools involved and the results to expect.

## Links

- [Assistants](https://invitas.co/asistentes)
- [Developers and REST API](https://invitas.co/developers) · [OpenAPI specification](https://invitas.co/api/openapi.json)
- [Privacy policy](https://invitas.co/privacidad) · [Sub-processors](https://invitas.co/subprocesadores) · [Terms](https://invitas.co/terminos)
- [Help](https://invitas.co/ayuda) · Support: hola@invitas.co

## License

Documentation: [CC BY 4.0](LICENSE).
