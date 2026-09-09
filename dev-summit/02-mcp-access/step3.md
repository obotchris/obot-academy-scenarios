# Add a Custom MCP Server

So far you've added the **GitHub** MCP server from Obot's built-in catalog. Obot can also host your own **custom** MCP servers — including ones packaged as a container image that Obot runs for you.

In this step you'll add a custom server that runs the **PII demo** container. You'll use this same server later in **Block 5: Filtering Sensitive Data**, where it stands in as a local source of sensitive test data.

## Add the Server

1. In the Obot admin UI, go to **MCP Servers** and choose to add a new server (**Add Server** / **New MCP Server**)
2. Set the **runtime type** to **Container**
3. Fill in the fields below, using the copy button on each value.

**Name**

```
pii-local
```{{copy}}

**Image name**

```
ghcr.io/chrisurwin/piidemo:latest
```{{copy}}

**Port**

```
8000
```{{copy}}

Then click **Save**.

Obot pulls the image and runs the container as a hosted MCP server. Once it's up, `pii-local` appears in your **MCP Servers** list alongside the GitHub server, ready to connect to just like any other catalog server.

> Because this server is hosted by Obot, its traffic also flows through the gateway — so it's authenticated, authorised, and logged in the same way you'll see in Block 3.
