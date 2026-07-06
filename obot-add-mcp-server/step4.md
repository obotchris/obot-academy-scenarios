# Make a Tool Call and View the Audit Log

With Claude connected to Obot, you can now call GitHub MCP tools directly from the chat — and every call is recorded in Obot's audit log.

## Make a Request

Open a new chat in Claude Desktop and send a prompt such as:

> List my GitHub repositories

Claude will recognise that the `list_repositories` tool (provided by the GitHub MCP server through Obot) is the right tool for the job and ask for your approval before calling it — click **Allow**.

The call is routed through the Obot gateway and Claude returns a list of your repositories.

## View the Audit Log

Every tool call routed through the gateway is recorded.

1. In the Obot admin UI, navigate to **Audit** (or **Monitoring → Audit Log**)
2. You should see an entry for the `list_repositories` call

Each entry shows:

| Field | Description |
|-------|-------------|
| **Timestamp** | When the tool call was made |
| **User** | The authenticated user (or API key) that made the call |
| **MCP Server** | Which server handled the call (e.g. `github`) |
| **Tool** | The specific tool invoked (e.g. `list_repositories`) |
| **Status** | Whether the call succeeded or failed |

Because every call passes through the Obot gateway, you get a single, consistent place to monitor what your AI clients are doing.
