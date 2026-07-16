# View the Audit Log

Every tool call routed through the Obot gateway is recorded. The audit log lets you see exactly what was called, by whom, and when.

## Open the Audit Log

1. In the Obot admin UI, navigate to **Audit** (or **Monitoring → Audit Log**)
2. You should see an entry for the `list_repositories` call you made in the previous step (plus any follow-ups)

## Reading an Entry

Each entry shows:

| Field | Description |
|-------|-------------|
| **Timestamp** | When the tool call was made |
| **User** | The authenticated user (or API key) that made the call |
| **MCP Server** | Which server handled the call (e.g. `github`) |
| **Tool** | The specific tool invoked (e.g. `list_repositories`) |
| **Status** | Whether the call succeeded or failed |

## Why This Matters

Because every call passes through the Obot gateway, you get a single, consistent place to monitor what your AI clients are doing with your MCP servers — invaluable for security reviews, usage tracking, and debugging.
