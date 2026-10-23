# Connect invitas in Grok (grok.com)

[English](#english) · [Español](#español)

## English

### Requirements

A Grok account with connector access. Business and Enterprise users need their team administrator to provision the connector. You need an invitas account.

### Connect

1. Open [Grok Connectors](https://grok.com/connectors).
2. Select **New Connector → Custom** and enter `https://invitas.co/mcp`.
3. Complete the requested OAuth sign-in to invitas in the browser and review consent.
4. Start a conversation and ask Grok to use invitas.

invitas uses Streamable HTTP and OAuth 2.1 with PKCE and dynamic client registration. Review the permissions before authorising.

### Verify

Ask: **“Use invitas to list my events and their names. Do not change anything.”** Check that invitas called `list_events` and returned your events, or an empty list. A reply without a tool call does not verify access.

### Disconnect and revoke

Remove or disconnect the custom connector from Grok Connectors. Team provisioning is managed by the administrator. To revoke access at invitas, open [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Removing client configuration alone does not revoke the grant. See [Data and permissions](../privacy.md).

### Common issues

No custom option: check account or team access. Use the full public `/mcp` URL. If authorization fails, retry sign-in rather than entering an API key.

## Español

### Requisitos

Cuenta de Grok con acceso a conectores. En Business y Enterprise, el administrador del equipo debe habilitar el conector. Necesitas una cuenta de invitas.

### Conectar

1. Abre [Grok Connectors](https://grok.com/connectors).
2. Elige **New Connector → Custom** e introduce `https://invitas.co/mcp`.
3. Completa el inicio de sesión OAuth de invitas en el navegador y revisa el consentimiento.
4. Abre una conversación y pide a Grok que use invitas.

invitas usa Streamable HTTP y OAuth 2.1 con PKCE y registro dinámico de clientes. Revisa los permisos antes de autorizar.

### Verificar

Pregunta: **«Usa invitas para listar mis eventos y sus nombres. No cambies nada».** Comprueba que invitas llamó a `list_events` y devolvió tus eventos o una lista vacía. Una respuesta sin llamada a herramienta no verifica el acceso.

### Desconectar y revocar

Elimina o desconecta el conector personalizado en Grok Connectors. El administrador gestiona la configuración del equipo. Para revocar el acceso en invitas, abre [Mi cuenta](https://invitas.co/dashboard/account) → **Apps conectadas → Desconectar**. Eliminar la configuración del cliente no revoca el permiso. Consulta [Datos y permisos](../privacy.md).

### Problemas comunes

Sin opción personalizada: revisa el acceso de la cuenta o equipo. Usa la URL pública completa con `/mcp`. Si falla la autorización, repite el login en lugar de introducir una clave API.

<!-- Official sources consulted: 2026-10-22 (America/Bogota).
https://docs.x.ai/grok/connectors
https://docs.x.ai/grok/connector-management
-->

Sources / Fuentes: [Official documentation 1](https://docs.x.ai/grok/connectors) · [Official documentation 2](https://docs.x.ai/grok/connector-management)
