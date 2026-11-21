---
name: setup
description: Connect Morton Street to this agent and sign in. Use when the mortonstreet tools are missing, a tool says to sign in, or the user asks how to connect Morton Street to Claude, Claude Code, ChatGPT, Codex or Cursor.
---

# Set up Morton Street

The Morton Street MCP server is hosted at `https://api.mortonstreet.ai/mcp`. There is nothing to
install: the agent connects over HTTP and the user signs in with their Morton Street account in
the browser.

## Claude Code

With this plugin installed the server is already configured. Run `/mcp`, pick **mortonstreet**
and choose **Authenticate**. Without the plugin:

```
claude mcp add --transport http mortonstreet https://api.mortonstreet.ai/mcp
```

## Claude, ChatGPT, Cursor

Add a custom connector with the URL `https://api.mortonstreet.ai/mcp`, then sign in when asked.
Step-by-step guides: https://docs.mortonstreet.ai/connect/claude

## Check it worked

Call `whoami`. It returns the user and the workspaces they belong to. If it lists no workspaces,
the user has not been invited to one yet: an admin invites them from the portal at
https://app.mortonstreet.ai under **Settings → Members**.
