# Add a Custom MCP Server

So far you've added the **GitHub** MCP server from Obot's built-in catalog. Obot can also host your own **custom** MCP servers — including ones packaged as a container image that Obot runs for you.

In this step you'll add a custom server that runs the **PII demo** container. You'll use this same server later in **Block 5: Filtering Sensitive Data**, where it stands in as a local source of sensitive test data.

## Add the Server

1. In the Obot admin UI, go to **MCP Servers** and choose to add a new server (**Add Server** / **New MCP Server**)
2. Give it a **name** of `pii-local`
3. Set the **runtime type** to **Container**
4. Fill in the container details:
   - **Image name** — `ghcr.io/chrisurwin/piidemo:latest`
   - **Port** — `8000`
5. Click **Save**

Obot pulls the image and runs the container as a hosted MCP server. Once it's up, `pii-local` appears in your **MCP Servers** list alongside the GitHub server, ready to connect to just like any other catalog server.

> Because this server is hosted by Obot, its traffic also flows through the gateway — so it's authenticated, authorised, and logged in the same way you'll see in Block 3.
