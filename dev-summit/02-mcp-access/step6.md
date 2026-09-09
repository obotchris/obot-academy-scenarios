# Connect the Composite Server and See Tool Restrictions in Action

You've created the `pii-filtered` composite server, which exposes only the `get` tool from `pii-local`. Now connect it to Claude Code the same way you connected the other servers, and see how the disabled tools change what Claude can do.

## Step 1: Get the Gateway Connection String

1. In Obot, under **MCP Servers** open the `pii-filtered` server.
2. Click **Connect to Server**
3. Copy the connection string shown in the dialog or click the button to add it to the clients that support that method.

## Step 2: Add the Server to Claude Code

Add `pii-filtered` as an HTTP MCP server in Claude Code, using the connection URL from the dialog:

```bash
claude mcp add --transport http "pii-filtered" "<connection URL from the Connect to Server dialog>"
```{{copy}}

You can verify that the server is now present in claude by typing the following command

```bash
claude mcp list
```{{copy}}

## Step 3: Fetch a Single Customer (Succeeds)

In a Claude Code session, ask for a specific customer:

>```get customer 1 using pii-filtered```{{copy}}

As with the other servers, the first time you do this you may be prompted to authenticate — click the Obot redirect link and complete the flow.

Claude uses the `get` tool (the one you left enabled) and — after you **Allow** the call — returns the record for customer 1. This works because `get` is exposed by the composite server.

## Step 4: List All Customers (Fails)

Now try to list everyone:

> ```list all customers using pii-filtered```{{copy}}

This time the request **fails**. Because you turned off the `search` and `list` tools on the composite server, there is no tool available for Claude to call — so it cannot list or search the customer data, even though the underlying `pii-local` container still supports it.

## Why This Matters

The backing `pii-local` server can `get`, `search`, and `list`, but `pii-filtered` only exposes `get`. Clients connecting through the composite server are limited to exactly the tools you allowed — a clean way to enforce least-privilege access without changing the underlying server.
