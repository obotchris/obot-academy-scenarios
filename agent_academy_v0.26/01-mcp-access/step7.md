# Connect the Curated vMCP & See Tool Restrictions in Action

You've created the `pii-filtered` vMCP, which exposes only the `get` tool from `pii-local`. Now connect it to Claude Code the same way you connected the `github` vMCP, and see how the disabled tools change what Claude can do.

## Step 1: Get the Connection URL

1. Open the `pii-filtered` vMCP and click **Connect**
2. Click **Continue** / **Configure** if prompted, and supply any fields marked **Provided at connection**
3. Copy the **Connection URL** from the dialog

## Step 2: Add the vMCP to Claude Code

```bash
claude mcp add --transport http "pii-filtered" "<connection URL from the Connect dialog>"
```{{copy}}

Verify it's present:

```bash
claude mcp list
```{{copy}}

## Step 3: Fetch a Single Customer (Succeeds)

In a Claude Code session, ask for a specific customer:

```bash
get customer 1 using pii-filtered
```{{copy}}

As with the other servers, the first time you do this you may be prompted to authenticate — click the Obot redirect link and complete the flow.

Claude uses the `get` tool (the one you left enabled) and — after you **Allow** the call — returns the record for customer 1. This works because `get` is exposed by the vMCP.

## Step 4: List All Customers (Fails)

Now try to list everyone:

```bash
list all customers using pii-filtered
```{{copy}}

This time the request **fails**. Because you turned off the `search` and `list` tools on the vMCP, there is no such tool for Claude to call — so it cannot list or search the customer data, even though the underlying `pii-local` container still supports it.

## Why This Matters

The backing `pii-local` server can `get`, `search`, and `list`, but the `pii-filtered` vMCP only exposes `get`. Clients connecting through the vMCP are limited to exactly the tools you allowed — a clean way to enforce least-privilege access without changing the underlying server.
