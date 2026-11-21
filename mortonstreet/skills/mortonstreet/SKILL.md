---
name: mortonstreet
description: Morton Street — one sales workspace per client across HubSpot, Salesforce, Odoo, Shopify, Instantly, Smartlead and HeyReach. Use whenever the user mentions Morton Street, a client workspace, contacts, companies, deals, the pipeline, campaigns, replies, or syncing a CRM or sequencer. Routes to the setup and approvals skills.
---

# Morton Street

Morton Street keeps one workspace per client. Each workspace pulls contacts, companies, deals,
campaigns and activity from that client's tools into one shared model, so you can ask one
question across all of them. Everything here goes through the `mortonstreet` MCP server.

Not connected yet, or a tool says to sign in? Use the **setup** skill.

## Pick the workspace first

Call `whoami` at the start. It names the active workspace and the others you can use. If the
user means a different client, call `switch_workspace` with its id or name before anything else.
Never mix two clients' data in one answer.

## Reading (safe, no approval needed)

| The user wants | Call |
| --- | --- |
| Find people | `search_contacts`, then `get_contact` for one person |
| Find companies | `search_companies` |
| Everything about one account | `account_timeline` |
| The pipeline | `get_pipeline` |
| Campaigns and how they perform | `list_campaigns`, `campaign_performance` |
| Who replied but has no deal | `replied_without_deal` |
| Which tools are connected | `list_connections` |

If numbers look stale, `sync_now` pulls fresh data from the connected tools.

## Changing data (needs the user's yes)

`upsert_contacts`, `create_deal`, `update_deal_stage`, `log_activity`, `push_leads_to_sequence`,
`sync_to_crm` and `list_to_sequence_and_crm` may return a preview instead of running. Follow the
**approvals** skill: show the preview, wait for a clear yes, then `confirm_action`.

## Style

The people using this are not technical. Answer in plain language: names, companies, amounts and
dates. Don't show ids, field names or JSON unless asked.
