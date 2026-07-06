# Obot Academy Scenarios

A collection of interactive scenarios for learning [Obot](https://obot.ai), the open-source MCP (Model Context Protocol) platform. These scenarios run on **Obot Academy**, where a running Obot instance is provided for each learner — there is nothing to install or start.

Based on [chrisurwin/killacoda](https://github.com/chrisurwin/killacoda).

## Scenarios

| Scenario | Description |
|----------|-------------|
| [`obot-github-auth`](./obot-github-auth) | Set up GitHub as an OAuth authentication provider |
| [`obot-google-auth`](./obot-google-auth) | Set up Google as an OAuth authentication provider |
| [`obot-add-mcp-server`](./obot-add-mcp-server) | Add an MCP server from the catalog, connect a client, and view the audit log |
| [`obot-add-llm`](./obot-add-llm) | Configure an LLM model provider and test it in the built-in chat |

## Scenario structure

Each scenario is a directory containing:

- `index.json` — scenario metadata and step order
- `intro.md` — introduction shown before the steps
- `step*.md` — the individual steps
- `finish.md` — closing screen
- `thumbnail.png` — scenario thumbnail

The two auth scenarios assume Obot is running with authentication enabled, so they begin by logging in with the bootstrap token surfaced in the environment. The MCP and LLM scenarios go straight to the admin UI.

For more details, visit the [Obot documentation](https://docs.obot.ai).
