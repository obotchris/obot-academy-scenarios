# Create a Composite MCP Server

Obot can combine one or more existing MCP servers into a **composite** server — a single server that exposes a curated subset of the underlying servers' tools. This lets you decide exactly which tools are available to clients, rather than exposing everything the backing server offers.

In this step you'll create a composite server called `pii-filtered` that wraps the `pii-local` server you created earlier, but exposes **only** its `get` tool — the `search` and `list` tools will be turned off.

## Create the Server

1. In the Obot admin UI, go to **MCP Servers** and choose to add a new server (**Add Server** / **New MCP Server**)
2. Give it a **name** of ```pii-filtered```{{copy}}
3. Set the **runtime type** to **Composite**
4. Add `pii-local` as a backing server so the composite has access to its tools

## Restrict the Tools

1. In the composite server's tool list, review the tools inherited from `pii-local` (e.g. `get`, `search`, `list`)
2. **Turn off** the `search` and `list` tools
3. Leave the `get` tool **enabled**
4. Click **Save**

`pii-filtered` now appears in your **MCP Servers** list. It routes to the same `pii-local` container, but only the `get` tool is exposed — so clients can fetch a specific customer, but cannot search or list all of them.

> Composite servers are a simple way to enforce least-privilege at the tool level: expose only the operations a client actually needs, and keep the rest off the table entirely.
