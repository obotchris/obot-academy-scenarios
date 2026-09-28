# Generate GitHub PAT

The first thing to do is add the **GitHub** MCP server. In v0.26 you add the server, and then in the next step you expose it to clients through a Virtual MCP (vMCP).

## Step 1: Create a GitHub Personal Access Token

The GitHub MCP server needs a GitHub Personal Access Token (PAT) to reach your repositories.

1. Go to [GitHub Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)
2. Click **Generate new token (classic)**
3. Name it (e.g. `Obot`) and select the **repo** scope
4. Click **Generate token** and copy the value
5. Make a note of the token — you'll supply it the first time you use the GitHub server through Obot

> **Why a vMCP?** In v0.26, clients connect through Virtual MCPs, not directly to servers. A vMCP lets you aggregate servers, rename or hide individual tools, and grant access per user or group — all behind one connection URL.
