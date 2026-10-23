# Connect invitas in Windsurf / Cascade

[English](#english) · [Español](#español)

## English

### Requirements

The Cascade agent with MCP enabled. Current Windsurf documentation redirects to Devin Desktop; this setup is for Cascade. You need an invitas account.

### Connect

1. In Cascade, open **… (Actions) → MCPs → Open MCP config file**.
2. Merge this entry into the opened `mcp_config.json`:

```json
{
  "mcpServers": {
    "invitas": {
      "serverUrl": "https://invitas.co/mcp"
    }
  }
}
```

3. Save, enable invitas in the MCPs section, and follow the OAuth sign-in prompt in your browser.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Remove invitas from the opened MCP configuration and save. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

If your tab uses Devin Local, its MCP configuration is different; switch to Cascade for this guide. Missing tools: check the server toggle, team policy, and Cascade's total tool limit.

## Español

### Requisitos

El agente Cascade con MCP habilitado. La documentación actual de Windsurf redirige a Devin Desktop; esta configuración corresponde a Cascade. Necesitas una cuenta de invitas.

### Conectar

1. En Cascade, abre **… (Actions) → MCPs → Open MCP config file**.
2. Integra esta entrada en el `mcp_config.json` que se abre:

```json
{
  "mcpServers": {
    "invitas": {
      "serverUrl": "https://invitas.co/mcp"
    }
  }
}
```

3. Guarda, habilita invitas en la sección MCPs y completa el acceso OAuth desde el navegador.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Elimina invitas de la configuración MCP abierta y guarda. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Si la pestaña usa Devin Local, su configuración MCP es distinta; usa Cascade para esta guía. Sin herramientas: revisa el interruptor, la política del equipo y el límite total de herramientas de Cascade.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://docs.windsurf.com/windsurf/cascade/mcp
https://docs.devin.ai/desktop/cascade/mcp
-->

Sources / Fuentes: [Official documentation 1](https://docs.windsurf.com/windsurf/cascade/mcp) · [Official documentation 2](https://docs.devin.ai/desktop/cascade/mcp)
