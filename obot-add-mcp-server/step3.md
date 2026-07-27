# Connect an AI Client

Claude Code supports remote MCP servers. In this step you point Claude Code at your Obot MCP gateway so it can reach the GitHub MCP server you just added.

## Step 1: Get Your Obot Gateway Connection String

1. In Obot, open the GitHub MCP server you added under **MCP → Servers**
2. Click **Connect to Server**
3. Copy the connection string shown in the dialog

## Step 2: Add the Gateway to Claude Code

Add the Obot gateway as an MCP server in Claude Code, using the connection string from the dialog:

```bash
claude mcp add github-obot -- npx mcp-remote <string from the Connect to Server dialog>
```

## Step 3: Authenticate and Confirm

The first time Claude Code connects, `mcp-remote` opens your browser to authenticate to the Obot gateway. Approve the connection, then confirm the server is connected:

```bash
claude mcp list
```

> `mcp-remote` bridges Claude Code's local MCP transport to Obot's remote gateway, handling the OAuth handshake for you.
