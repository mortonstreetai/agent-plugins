<p align="center"><strong>Morton Street from your AI agent</strong>: skills and the Morton Street MCP server for Claude Code, Codex and Cursor.</p>

<p align="center"><a href="https://docs.mortonstreet.ai">Docs</a> · <a href="GETTING_STARTED.md">Getting started</a></p>

---

Paste this into your agent:

```
Set up the Morton Street plugin by following the steps in https://github.com/mortonstreetai/agent-plugins
```

It connects the Morton Street MCP server and signs you in through your browser. Then ask:

> What's in the pipeline for MCS this month?

> Who replied to our campaigns in the last two weeks but doesn't have a deal yet?

## Install by hand

**Claude Code**

```
/plugin marketplace add mortonstreetai/agent-plugins
/plugin install mortonstreet@mortonstreet-plugins
```

Then run `/mcp`, pick **mortonstreet** and choose **Authenticate**.

**Codex**

```
codex plugin marketplace add mortonstreetai/agent-plugins
```

Then open **Plugins** and install **mortonstreet**.

**Claude, ChatGPT or any other MCP client:** add a custom connector with
`https://api.mortonstreet.ai/mcp`.

## What's inside

| Skill | For |
| --- | --- |
| `mortonstreet` | What Morton Street does and which tool answers which question |
| `setup` | Connect the agent and sign in |
| `approvals` | Previews, confirming and cancelling writes |

Full tool reference: https://docs.mortonstreet.ai/mcp/overview
