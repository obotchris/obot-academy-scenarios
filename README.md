# Obot Academy Scenarios

A collection of interactive scenarios for learning [Obot](https://obot.ai), the open-source MCP (Model Context Protocol) platform. These scenarios run on **Obot Academy**, where a running Obot instance is provided for each learner — there is nothing to install or start.

Based on [chrisurwin/killacoda](https://github.com/chrisurwin/killacoda).

## Scenarios

| Scenario | Description |
|----------|-------------|
| [`agent_academy_v0.26`](./agent_academy_v0.26) | **Obot v0.26** end-to-end walkthrough: local first-login (detected email + set password) → add the GitHub MCP server → expose it through a Virtual MCP (vMCP) → test it with the built-in MCP inspector → connect Claude Code via the gateway → add a custom container server → curate tools with a vMCP → audit gateway traffic → enroll Obot Sentry (scan, hooks, forward local logs, enforce policy) → filter sensitive data with gateway filters |
| [`dev-summit`](./dev-summit) | Earlier five-block walkthrough (pre-vMCP): bootstrap login → GitHub auth → GitHub MCP + composite servers → audit → Obot Sentry → filters |
| [`obot-workshop`](./obot-workshop) | Full end-to-end walkthrough: bootstrap login → GitHub auth → add the GitHub MCP server to Claude Code → query repositories → view the audit log → add a source catalog → enroll the Obot Sentry client → scan inventory → automate with hooks → forward local MCP audit logs → filter sensitive data with gateway filters |
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

The two auth scenarios assume Obot is running with authentication enabled, so they begin by logging in with the bootstrap token surfaced in the environment. The MCP and LLM scenarios go straight to the admin UI.

For more details, visit the [Obot documentation](https://docs.obot.ai).
