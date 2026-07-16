# Query GitHub for Your Repositories

With Claude connected to Obot, you can now call GitHub MCP tools directly from the chat.

## Make a Request

Open a new chat in Claude Desktop and send a prompt such as:

> List my GitHub repositories

Claude will recognise that the `list_repositories` tool (provided by the GitHub MCP server through Obot) is the right tool for the job and ask for your approval before calling it — click **Allow**.

The request is routed through the Obot gateway to the GitHub MCP server, and Claude returns your repositories:

```
Here are your GitHub repositories:

• my-project — last updated 2 days ago
• another-repo — last updated 1 week ago
• ...
```

## Try a Follow-up

You can chain more GitHub tool calls in the same conversation, for example:

> Show me the open issues in my-project

Each call goes through the Obot gateway, where it is authenticated, authorised, and logged — which you'll verify in the next step.
