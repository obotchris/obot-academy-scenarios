# Add the GitHub MCP Server to Claude

Next, add the **GitHub** MCP server from Obot's catalog and connect Claude Code to it through the Obot gateway.

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
5. Make a note of the token as it will be used the first time you query **Github**

## Step 3: Get the Gateway Connection String

1. In Obot, under **MCP Servers** open the GitHub MCP server.
2. Click **Connect to Server**
3. Copy the connection string shown in the dialog or click the button to add it to the clients that support that method.

## Step 4: Add the Gateway to Claude Code

Add the Obot gateway as an HTTP MCP server in Claude Code, using the connection URL from the dialog:

```bash
claude mcp add --transport http "github-obot" "<connection URL from the Connect to Server dialog>"
```{{copy}}

You can verify that the server is now present in claude by typing the following command

```bash
claude mcp list
```{{copy}}




