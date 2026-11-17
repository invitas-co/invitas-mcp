# invitas MCP connector

[Español](README.es.md)

![invitas MCP Connector Protocol](docs/images/mcp-terminal-inspector.webp)

Official Model Context Protocol (MCP) server for [invitas.co](https://invitas.co). Create, customize, and manage your invitations, guest rosters, RSVPs, and table seating through conversation with Claude, ChatGPT, Cursor, and any MCP-compliant client.

**Connector Endpoint:** `https://invitas.co/mcp` (Streamable HTTP / JSON-RPC 2.0)

---

## Architecture & Interaction Flow

The connector authenticates requests through OAuth 2.1 (PKCE) or Personal Access Tokens (PAT).

```mermaid
sequenceDiagram
    autonumber
    actor User as Host / Developer
    participant Client as MCP Client (Claude / ChatGPT / Cursor)
    participant Connector as invitas MCP Server (https://invitas.co/mcp)
    participant App as invitas.co Core API

    User->>Client: "How many guests confirmed for my event?"
    Client->>Connector: POST /mcp (tools/call: list_guests)
    Connector->>App: GET /api/v1/events/{id}/guests (Bearer Token)
    App-->>Connector: 200 OK (guests & RSVPs payload)
    Connector-->>Client: 200 OK (JSON-RPC tool result)
    Client-->>User: "You have 26 confirmed guests out of 41 invited."
```

---

## Tools

The [tool catalogue](docs/tools.md) lists the tools and scopes. Availability depends on the event and the features enabled for the account.

## Claude plugin

The [invitas plugin](plugins/invitas) bundles the connection and two skills for getting started and building a custom invitation from an idea, HTML or a PDF attachment.

---

## Client Configuration Examples

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

### Direct HTTP Request Example

```sh
# Discover available tools
curl -X POST https://invitas.co/mcp \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_PERSONAL_ACCESS_TOKEN" \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "tools/list"}'
```

---

## Supported Assistants

Step-by-step connection guides for every major client:

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

---

## Sign-in and Permissions

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

---

## What the Assistant Sees, and How to Disconnect

Within the permissions you authorise, your assistant can access the event information you see in your dashboard, including guest contact details, invitation links, wall messages, tables and prepared reminders. When you connect and authorise access, that information can be shared with your assistant provider, such as Anthropic for Claude or OpenAI for ChatGPT. To end access immediately, open [Mi cuenta](https://invitas.co/dashboard/account), select **Apps conectadas**, then **Desconectar**; changes already made are kept. See [Data and permissions](docs/privacy.md) for details.

---

## Examples

See [example conversations](examples/conversations.md) for requests you can make, the tools involved and the results to expect.

---

## Links

- [Assistants](https://invitas.co/asistentes)
- [Developers and REST API](https://invitas.co/developers) · [OpenAPI specification](https://invitas.co/api/openapi.json)
- [Privacy policy](https://invitas.co/privacidad) · [Sub-processors](https://invitas.co/subprocesadores) · [Terms](https://invitas.co/terminos)
- [Help](https://invitas.co/ayuda) · Support: hola@invitas.co

---

## Repository Development

This repository contains documentation and a generated tool catalogue; the hosted connector runs in the invitas application. With Node.js 22 installed, run `npm run check` to verify that generated catalogue files match their source. Run `npm run catalog` after editing `docs/catalog.source.json` to regenerate them. See [CONTRIBUTING.md](CONTRIBUTING.md).

The `docs/` directory contains the catalogue and client guides, `examples/` contains conversations, and `scripts/` contains the catalogue generator. Changes to this repository publish documentation through the repository; deploying the hosted connector is handled by the application repository.

---

## License

Documentation: [CC BY 4.0](LICENSE).
