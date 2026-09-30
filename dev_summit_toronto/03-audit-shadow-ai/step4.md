# Forward Local MCP Logs to Obot

Labs A and B went through the gateway, so every call was logged centrally. Now add a purely **local** MCP server that never touches Obot — and watch Sentry forward its activity anyway.

## Step 1: Add a Local MCP Server to Claude Code

This server runs on your machine via `npx` and does **not** go through Obot:

```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/a/folder
```{{copy}}

Replace `/path/to/a/folder` with a directory the server is allowed to read.

## Step 2: Use the Server and Force an MCP Call

Navigate to that folder and confirm the server is connected:

```bash
claude mcp list
```{{copy}}

Start a Claude Code session from there and send:

> List the files in this folder using the filesystem mcp.

**Say "using the filesystem mcp"** — otherwise Claude will use built-in file reads and you'll see nothing. Approve the call when prompted.

## Step 3: See the Forwarded Logs in Obot

Open Obot's **Audit** log. Alongside your gateway entries from Labs A and B, you now see the **local** filesystem call — forwarded by Sentry and attributed to your device and user.

> 🧠 **Debrief:** without Sentry, that call would be invisible to the org. Now local and gateway MCP activity land in one audit trail.
