---
name: approvals
description: How Morton Street writes are approved. Use whenever a mortonstreet tool returns status pending_confirmation with an action_id, or before adding leads to a campaign, syncing contacts to a CRM, or changing deals.
---

# Approvals

Writes that send email, add leads to a campaign or change many records come back as a preview
with an `action_id` instead of running. Nothing has happened yet.

1. Show the user the `summary` and the important parts of the `preview` in plain words: how many
   people, which campaign or CRM, and anything that was skipped.
2. Ask for a clear yes. Silence, "maybe" or a question is not a yes.
3. On yes, call `confirm_action` with the `action_id`. It runs exactly what was previewed, once.
4. On no, call `cancel_action`.

Previews expire after 30 minutes. `list_pending_actions` shows what is still waiting; teammates
can also approve or reject them in the portal under **Approvals**.
