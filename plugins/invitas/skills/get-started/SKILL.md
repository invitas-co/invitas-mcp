---
name: get-started
description: Connect invitas and choose an event to manage its invitation and guests. Conecta invitas y elige un evento. Conecte o invitas e escolha um evento.
---

Reply in the host's language. Keep tool names and input keys as written.

## Español

1. Conecta la cuenta mediante OAuth. Consulta `guide` y `list_events` y deja que el anfitrión elija el evento. Antes de editar, lee `get_event`. Para crear un borrador, consulta `list_templates`.
2. `update_event` combina `config` por clave de primer nivel. Si envías una lista o un mapa, conserva los elementos que el anfitrión no pidió cambiar.
3. Para HTML propio o para rehacer un PDF como invitación, usa la skill `custom-invitation`.
4. Para fijar o quitar el idioma de invitados seleccionados, usa `set_guests_language` si aparece. Requiere Cinemático y que el idioma esté habilitado. El texto del anfitrión queda en el idioma en que se escribió.

## English

1. Connect through OAuth. Use `guide` and `list_events` and let the host choose the event. Read `get_event` before editing. Check `list_templates` before creating a draft.
2. `update_event` merges `config` by top-level key. When sending a list or map, preserve entries the host did not ask to change.
3. For custom HTML or rebuilding a PDF as an invitation, use the `custom-invitation` skill.
4. Set or clear the language for selected guests with `set_guests_language` when listed. This requires Cinemático and an enabled language. The host's text stays in its original language.

## Português

1. Conecte a conta por OAuth. Consulte `guide` e `list_events` e deixe a pessoa anfitriã escolher o evento. Leia `get_event` antes de editar. Consulte `list_templates` antes de criar um rascunho.
2. `update_event` combina `config` por chave de primeiro nível. Ao enviar uma lista ou um mapa, preserve os itens que a pessoa anfitriã não pediu para alterar.
3. Para usar HTML próprio ou recriar um PDF como convite, use a skill `custom-invitation`.
4. Use `set_guests_language`, quando disponível, para definir ou remover o idioma de convidados selecionados. O recurso exige Cinemático e um idioma habilitado. Os textos da pessoa anfitriã permanecem no idioma original.

Use the client's OAuth flow for sign-in. Confirm changes that affect guests, including publishing, and use personal links only for the authorized task. Collect logistical information only. For a 402, explain the event's plan restriction. Payments and deletions are managed from the invitas dashboard.
