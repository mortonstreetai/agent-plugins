# Getting started

These are the steps an agent follows when asked to set up Morton Street.

1. **Connect the server.** Claude Code: `claude mcp add --transport http mortonstreet https://api.mortonstreet.ai/mcp`
   (skip if the plugin is installed). Other clients: add a custom connector with that URL.
2. **Sign in.** Claude Code: `/mcp` → **mortonstreet** → **Authenticate**. A browser window opens;
   sign in with the Morton Street account you were invited with.
3. **Check.** Call `whoami`. It should list at least one workspace. If it lists none, ask a
   workspace admin to invite you from https://app.mortonstreet.ai.
4. **Try it.** Ask for the pipeline (`get_pipeline`) or recent campaign results (`campaign_performance`).
