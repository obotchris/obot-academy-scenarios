# Create a vMCP for GitHub

Now expose the GitHub server to clients by wrapping it in a **Virtual MCP (vMCP)**. The vMCP is what clients (and Obot's own MCP inspector) connect to.

## Create the vMCP

1. In the Obot admin UI, go to **All Resources → vMCPs**
2. Click **Create vMCP**
3. Choose the **GitHub** entry from the catalog and drag it to the **+CREATE NEW VMCP** in the centre
4. Give it a name and click **Create**
5. On the next screen you will need your GitHub PAT, paste this in the box, and also drop down the endpoint path and select **Default**, then click **Next**
6. you now get the choice of **As-Is** or **Managed** for now choose **As-Is**

The GitHub server now appears in your **MCP Servers** list. On its own it isn't yet reachable by a client — in the next step you'll expose it through a vMCP.s tools.

## Review the Exposed Tools

Open the `github` vMCP and look at the GitHub component's tool list. This is where you control what clients see — for each tool you can:

- **Disable** it (so no client connecting through this vMCP can call it)
- **Rename** it or change its description
- **Add a prefix** to avoid name collisions when several servers are combined

For now, **leave all the GitHub tools enabled** — you'll practise curating tools with a second vMCP later in this block.

> **Profiles, briefly:** access and tool grants come from **profiles** on the vMCP. The default profile covers you as admin. To share this vMCP with a team you'd add a profile targeting a user, group, or **All Obot Users** and select which tools it grants. Grants are additive — a user who matches several profiles gets the combined set.
