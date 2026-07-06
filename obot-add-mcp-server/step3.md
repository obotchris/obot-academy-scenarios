# Connect an AI Client

Claude Desktop (and Claude.ai) supports remote MCP servers. In this step you point Claude at your Obot MCP gateway so it can reach the GitHub MCP server you just added.

## Step 1: Get Your Obot Gateway Connection String

1. In Obot, open the GitHub MCP server you added under **MCP → Servers**
2. Click **Connect to Server**
3. Copy the connection string shown in the dialog

## Step 2: Configure Claude Desktop

Open the Claude Desktop configuration file:

- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

Add the Obot gateway as an MCP server:

```json
{
  "mcpServers": {
    "github-obot": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "<string from the Connect to Server dialog>"
      ]
    }
  }
}
```

## Step 3: Restart Claude Desktop

Fully quit and relaunch Claude Desktop. When it launches it should prompt you to authenticate to the Obot gateway. Approve the connection.

> `mcp-remote` bridges Claude Desktop's local MCP transport to Obot's remote gateway, handling the OAuth handshake for you.
