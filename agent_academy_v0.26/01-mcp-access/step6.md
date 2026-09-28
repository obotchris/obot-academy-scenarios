# Curate Tools with a vMCP

A vMCP doesn't just aggregate servers — it lets you decide **exactly which tools** clients can use. This replaces the old "composite server" model: instead of a separate composite resource, you simply disable the tools you don't want a vMCP to expose.

In this step you'll create a second vMCP called `pii-filtered` that wraps the `pii-local` server, but exposes **only** its `get` tool — the `search` and `list` tools will be turned off.

## Create the vMCP

1. Go to **vMCPs** and click **Create vMCP**
2. From the **MCP Servers** panel, **drag `pii-local`** onto the canvas to add it as a component
3. Give the vMCP this **name**:

```
pii-filtered
```{{copy}}

4. Click **Create**

## Turn Off the Tools You Don't Want

1. Open the `pii-filtered` vMCP and select the `pii-local` component
2. Review the tools it inherits (e.g. `get`, `search`, `list`)
3. **Disable** the `search` and `list` tools at the component level — disabling here prevents **every** profile from using them
4. Leave the `get` tool **enabled**
5. Save

`pii-filtered` now routes to the same `pii-local` container, but only the `get` tool is exposed — so clients can fetch a specific customer, but cannot search or list all of them.

> **Least privilege, the v0.26 way:** the backing server still supports `get`, `search`, and `list`, but this vMCP surfaces only `get`. Expose the operations a client actually needs and keep the rest off the table — no changes to the underlying server required. You can verify this immediately with the **MCP inspector** (**Test vMCP**): the tool list shows only `get`.
