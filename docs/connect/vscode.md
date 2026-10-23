# Connect invitas in VS Code (GitHub Copilot)

[English](#english) · [Español](#español)

## English

### Requirements

VS Code with AI features enabled, a local folder open, and access to Copilot agent sessions. You need an invitas account.

### Connect

1. Run **MCP: Add Server** in the Command Palette.
2. Choose **HTTP (HTTP or Server-Sent Events)**, enter `https://invitas.co/mcp`, and name it `invitas`.
3. Select **Global**, then **Copilot Global** when offered. Review trust prompts and complete invitas OAuth sign-in in the browser.
4. In Copilot chat, open **Chat: Open Customizations → Tools** and enable invitas tools.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Remove invitas from the configuration destination chosen during setup. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

No Copilot Global: check the selected harness and organisation permissions. Inspect server output if sign-in fails; verify tools are enabled in the active session.

## Español

### Requisitos

VS Code con funciones de IA habilitadas, una carpeta local abierta y acceso a sesiones de agente de Copilot. Necesitas una cuenta de invitas.

### Conectar

1. Ejecuta **MCP: Add Server** desde la paleta de comandos.
2. Elige **HTTP (HTTP or Server-Sent Events)**, introduce `https://invitas.co/mcp` y ponle el nombre `invitas`.
3. Selecciona **Global** y luego **Copilot Global** cuando se ofrezca. Revisa la confianza e inicia sesión con OAuth de invitas en el navegador.
4. En Copilot, abre **Chat: Open Customizations → Tools** y habilita las herramientas de invitas.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Elimina invitas de la configuración que elegiste durante la instalación. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Sin Copilot Global: revisa el entorno de agente elegido y los permisos de la organización. Si falla el acceso, consulta la salida del servidor y habilita sus herramientas en la sesión activa.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://code.visualstudio.com/docs/agent-customization/mcp-servers
https://code.visualstudio.com/docs/agents/reference/mcp-configuration
-->

Sources / Fuentes: [Official documentation 1](https://code.visualstudio.com/docs/agent-customization/mcp-servers) · [Official documentation 2](https://code.visualstudio.com/docs/agents/reference/mcp-configuration)
