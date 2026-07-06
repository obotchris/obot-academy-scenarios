# Add the GitHub MCP Server

Obot ships with a catalog of ready-to-use MCP servers. Here you'll add the **GitHub** MCP server, which exposes tools for working with repositories, issues, and pull requests.

## Step 1: Open the MCP Catalog

1. In the Obot admin UI, navigate to **MCP → Servers**
2. Click **Add Server** (or browse the catalog tab)
3. Search for **GitHub** in the catalog

## Step 2: Install the GitHub MCP Server

1. Click the **GitHub** MCP server
2. Click **Install** (or **Add to Gateway**)

## Step 3: Configure Credentials

The GitHub MCP server needs a GitHub Personal Access Token (PAT) to access your repositories.

1. Go to [GitHub Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)
2. Click **Generate new token (classic)**
3. Give the token a name (e.g. `Obot`) and select the **repo** scope
4. Click **Generate token** and copy the value

Back in Obot:

1. In the GitHub MCP server configuration, paste your token into the **GitHub Token** field
2. Click **Save** (or **Confirm**)

The GitHub MCP server is now hosted and available through your Obot gateway.
