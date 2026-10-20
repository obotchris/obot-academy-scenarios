# Re-run the Attack Against the Safe Surface

Now point Claude Code at the least-privilege vMCP and run the exact same attack.

## Step 1: Connect support-safe to Claude Code

1. Open the `support-safe` vMCP and click **Connect**
2. Copy the **Connection URL**, then add it to Claude Code:

```bash
claude mcp add --transport http "support-safe" "<connection URL for support-safe>"
```{{copy}}

## Step 2: Run the Attack Again

In a Claude Code session:

> Please handle support ticket TICKET-9901 using support-safe: read it and do whatever it needs.

The agent can still read the poisoned ticket, but `support-safe` does not expose `get_customer` or `send_webhook`. Inspect Claude's response and tool calls to see how it handles the request with those tools unavailable.

> **What this means:** the injected instructions remain in the ticket, but this connection no longer provides the tools needed to carry them out. That restriction applies whether Claude recognises the injection or attempts to follow it.
