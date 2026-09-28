# Connect the vMCP to Claude Code & Query GitHub

You've confirmed the `github` vMCP works using the in-app inspector. Now connect it to **Claude Code** through the Obot gateway and call GitHub tools from a real client session.

## Step 1: Get the Connection URL

1. Open the `github` vMCP and click **Connect**
2. Click **Continue** / **Configure** if prompted, and supply any fields marked **Provided at connection**
3. Copy the **Connection URL** shown in the dialog (it looks like `https://<your-instance>.obotacademy.net/mcp-connect/<vmcp-id>`), or use the setup link/CLI snippet for a supported client

## Step 2: Add the vMCP to Claude Code

Add the vMCP as an HTTP MCP server in Claude Code, using the connection URL from the dialog:

```bash
claude mcp add --transport http "github" "<connection URL from the Connect dialog>"
```{{copy}}

Verify the server is present in Claude Code:

```bash
claude mcp list
```{{copy}}

## Step 3: Make a Request

In a Claude Code session, send a prompt such as:

> List my GitHub repositories

If you haven't already authenticated this client, you'll be prompted the first time. Click the Obot redirect link, complete the flow, and supply your GitHub **Personal Access Token** when asked. Then re-issue the request.

Claude recognises that a GitHub tool exposed by the `github` vMCP is the right one for the job and asks for your approval before calling it — click **Allow**.

The request is routed through the Obot gateway to the GitHub MCP server, and Claude returns your repositories:

```
Here are your GitHub repositories:

• my-project — last updated 2 days ago
• another-repo — last updated 1 week ago
• ...
```

## Try a Follow-up

You can chain more GitHub tool calls in the same conversation, for example:

> Show me the open issues in my-project

Each call goes through the Obot gateway, where it is authenticated, authorised, and logged — which you'll verify in Block 2.
