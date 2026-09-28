# Add a Custom Container MCP Server

So far you've added the **GitHub** server from Obot's catalog. Obot can also host your own **custom** MCP servers — including ones packaged as a container image that Obot runs for you.

In this step you'll add a custom server that runs the **PII demo** container. You'll expose it through vMCPs in the next two steps, and use it again in **Block 4: Filtering Sensitive Data**, where it stands in as a local source of sensitive test data.

## Add the Server

1. In the Obot admin UI, go to **AI Resources → MCP Servers** and click **Add MCP Server**
2. Choose to add a **Hosted Server** server and set the **runtime** to **Containerized**
3. Fill in the fields below, using the copy button on each value.

**Name**

```
pii-local
```{{copy}}

**Short Description**

```
pii-local
```{{copy}}

**Image (URI)**

```
ghcr.io/chrisurwin/piidemo:latest
```{{copy}}

**Port**

```
8000
```{{copy}}

**Path**

```
/mcp
```{{copy}}

Then click **Save**.

You will be prompted to add an Access Policy, just clikc **Continue** for now

Obot pulls the image and runs the container as a hosted MCP server. Once it's up, `pii-local` appears in your **MCP Servers** list alongside the GitHub server, ready to be added as a component to a vMCP.

> **Heads up:** adding an MCP server causes Obot to run code on the hosting backend, so only elevated roles (like the Owner) can do it. Because this server is hosted by Obot, its traffic also flows through the gateway — so it's authenticated, authorised, and logged in the same way you'll see in Block 2.
