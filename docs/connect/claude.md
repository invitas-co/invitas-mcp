# Connect invitas in Claude app and web / Claude app y web

[English](#english) · [Español](#español)

## English

### Requirements

A Claude account with custom connectors enabled. Free accounts have a one-connector limit. Team and Enterprise setup requires an authorised owner or administrator. You need an invitas account.

### Connect

1. On Claude web or Desktop, open **Customize → Connectors → + Add → Add custom connector**. In a team, an authorised owner first uses **Organization settings → Connectors → Add → Custom → Web**.
2. Enter **invitas** and `https://invitas.co/mcp`, then **Continue**. Review detected authentication.
3. Choose **Sign in now** and **Register automatically** for the OAuth client. Finish with **Add** and sign in to invitas in the browser. Members use **Connect** on the added connector.
4. Enable invitas from **+ → Connectors** in your conversation.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Disconnect invitas in **Customize → Connectors**; an organisation owner manages the shared definition. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

Missing connector controls: check plan limits and organisation policy. No tools in chat: enable the connector for that conversation.

## Español

### Requisitos

Cuenta de Claude con conectores personalizados habilitados. Las cuentas gratuitas tienen un límite de un conector. En Team y Enterprise, la configuración requiere un propietario o administrador autorizado. Necesitas una cuenta de invitas.

### Conectar

1. En Claude web o Desktop, abre **Customize → Connectors → + Add → Add custom connector**. En equipos, un propietario autorizado comienza en **Organization settings → Connectors → Add → Custom → Web**.
2. Introduce **invitas** y `https://invitas.co/mcp`; pulsa **Continue** y revisa la autenticación detectada.
3. Elige **Sign in now** y **Register automatically** como cliente OAuth. Termina con **Add** e inicia sesión en invitas en el navegador. Los miembros pulsan **Connect** en el conector agregado.
4. Habilita invitas desde **+ → Connectors** en la conversación.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Desconecta invitas en **Customize → Connectors**; el propietario gestiona la definición compartida. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

No aparecen los controles: revisa el límite del plan y la política de la organización. Sin herramientas: habilita el conector en esa conversación.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp
https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork
-->

Sources / Fuentes: [Official documentation 1](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp) · [Official documentation 2](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)
