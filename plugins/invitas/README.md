# invitas

Manage your events, invitations and guest lists in Claude with your invitas account. Use a template or, for eligible Animado and higher events, create your own invitation design. You can attach a PDF as a visual starting point, review the invitation before activation and keep tracking RSVPs and seating in the same event.

In Claude Code, add the marketplace and install the plugin.

```sh
claude plugin marketplace add invitas-co/invitas-mcp
claude plugin install invitas@invitas-co
```

In Claude Code, run `/mcp` and authenticate the invitas connection through OAuth. To choose an event, use `/invitas:get-started`. For an invitation design or a PDF attachment, use `/invitas:custom-invitation`. Both skills support Spanish, English and Portuguese.

The plugin connects to [invitas](https://invitas.co/asistentes). Changes to an invitation or its publication are made in your connected account. See the [privacy policy](https://invitas.co/privacidad) and [support](https://invitas.co/ayuda).
