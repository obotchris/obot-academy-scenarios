# Install a Local MCP Server and See Its Audit Logs Forwarded

In step 5 you saw that the GitHub MCP server ran through the **Obot gateway**, so every call was logged centrally. But developers also run MCP servers **locally** — configured straight into their AI client, running on their own machine, never touching the gateway. Normally that activity is a blind spot for the organisation.

Because you enrolled `obot-sentry` and installed its hooks, local MCP activity is now captured on the machine and its **audit logs are forwarded to your Obot server** — giving you the same visibility for local MCP servers as for gateway-hosted ones.

## Step 1: Add a Local MCP Server to Claude Code

Claude Code is one of the clients `obot-sentry` supports (along with Codex, VS Code, and Cursor). Add a local MCP server to Claude Code — it runs on your machine via `npx` and does **not** go through Obot:

```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/a/folder
```

Replace `/path/to/a/folder` with a directory on your machine the server is allowed to read.

## Step 2: Use the Server and Make a Tool Call

Start a Claude Code session in that directory and confirm the server is connected:

```bash
claude mcp list
```

Then send a prompt that uses the local server, for example:

> List the files in this folder

Claude Code calls the local filesystem MCP server. Approve the call when prompted.

## Step 3: See the Forwarded Audit Logs in Obot

Return to the Obot admin UI and open the **Audit** log.

Alongside the gateway entries from step 5, you'll now see entries for the **local** MCP server's tool calls — forwarded from your machine by `obot-sentry`. Because these originated locally rather than through the gateway, they're attributed to the device and user that `obot-sentry` reported them from.

## Why This Matters

Local MCP servers usually run outside any central control plane, so their tool calls never appear in an audit trail. With `obot-sentry` forwarding those logs to Obot, you get one place to see **all** MCP activity across your fleet — gateway-hosted and local alike.
