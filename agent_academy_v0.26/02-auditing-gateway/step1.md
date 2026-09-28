# View the Audit Log

Every tool call routed through the Obot gateway is recorded. The audit log lets you see exactly what was called, by whom, and when.

## Open the Audit Log

1. In the Obot admin UI, navigate to **MCP Management → Audit Logs**
2. You should see entries for the calls you made in Block 1 — the GitHub tool calls (e.g. listing repositories, `get_me`) and the `pii-filtered` `get` call, plus any follow-ups

> The tool calls you made from the **MCP inspector** appear here too. The inspector's *conversation* is ephemeral and isn't stored, but the *tool calls* still flow through the gateway and are audited like any other.

## Reading an Entry

Each entry shows:

| Field | Description |
|-------|-------------|
| **Timestamp** | When the tool call was made |
| **User** | The authenticated user (your detected email) that made the call |
| **MCP Server** | Which backing server handled the call (e.g. `github`, `pii-local`) |
| **Operation / Tool** | The specific tool invoked (e.g. `list_repositories`, `get`) |
| **Status** | Whether the call succeeded or failed |

Use the filters (date range, user, MCP server, operation type, status) to narrow the list. Opening an entry reveals the full request/response metadata — viewing full payloads requires the **Auditor** role.

## Why This Matters

Because every call passes through the Obot gateway — whether from an external client like Claude Code or from Obot's own inspector — you get a single, consistent place to monitor what your AI clients are doing with your MCP servers. That's invaluable for security reviews, usage tracking, and debugging.
