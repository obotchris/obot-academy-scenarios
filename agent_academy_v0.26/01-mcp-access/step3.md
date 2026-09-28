# Test the vMCP with the MCP Inspector

Before you wire up an external client, v0.26 lets you exercise a vMCP **directly inside Obot** with the built-in **MCP inspector** (also called the MCP tester). This is the fastest way to confirm a server works, see its tools, and make a real tool call — no Claude Code, no connection URL, nothing to install.

## Open the Inspector

1. Open the `github` vMCP you just created
2. Click **Inspector** Tab
3. If prompted, confirm the connection. Because this is the GitHub server's first use, you'll be asked to authenticate — complete the upstream GitHub flow and supply the **Personal Access Token** you created earlier when prompted

## Inspect the Tools

The inspector opens with two ways to drive the server:

- **An inspector panel** that lists the server's **tools, prompts, and resources**. You can select any tool, see its input schema, fill in arguments, and **invoke it individually** — great for checking a single tool in isolation.
- **A chat tab** wired to Obot's configured default model, where you can ask in natural language and let the model choose and call tools for you.

## Make a Real Tool Call

Try invoking a GitHub tool directly from the inspector panel — for example the tool that lists repositories or the one that returns the authenticated user (`get_me`). Run it and confirm real data comes back from GitHub.

Then try the **chat** panel with a prompt such as:

> List my GitHub repositories

The model picks the right GitHub tool, calls it through the vMCP, and shows your repositories inline.

> **Good to know:** inspector conversations are **ephemeral** — they aren't stored. But the **tool calls you make still flow through the gateway and appear in the audit log**, exactly like calls from an external client. You'll see these entries in Block 2.

Being able to test a vMCP in-app means you can validate a server — and later, that your tool curation and filters behave as intended — before handing a connection URL to anyone.
