# Add the GitHub MCP Server to Claude

Next, add the **GitHub** MCP server from Obot's catalog and connect Claude Desktop to it through the Obot gateway.

## Step 1: Install the GitHub MCP Server

1. In the Obot admin UI, navigate to **MCP → Servers**
2. Click **Add Server** (or browse the catalog tab) and search for **GitHub**
3. Click the **GitHub** MCP server, then click **Install** (or **Add to Gateway**)

## Step 2: Configure Credentials

The GitHub MCP server needs a GitHub Personal Access Token (PAT) to reach your repositories.

1. Go to [GitHub Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)
2. Click **Generate new token (classic)**
3. Name it (e.g. `Obot`) and select the **repo** scope
4. Click **Generate token** and copy the value
5. Back in Obot, paste the token into the **GitHub Token** field and click **Save**

## Step 3: Get the Gateway Connection String

1. In Obot, open the GitHub MCP server under **MCP → Servers**
2. Click **Connect to Server**
3. Copy the connection string shown in the dialog

## Step 4: Configure Claude Desktop

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

## Step 5: Restart Claude Desktop

Fully quit and relaunch Claude Desktop. When it launches it should prompt you to authenticate to the Obot gateway — approve the connection.

> `mcp-remote` bridges Claude Desktop's local MCP transport to Obot's remote gateway, handling the OAuth handshake for you.
