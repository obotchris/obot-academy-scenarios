# AgentCon SJC — Governing Enterprise AI Agents

**Workshop:** Governing Enterprise AI Agents with Obot — Tools, Exploits & Prompt Injection
**Platform:** Obot v0.26 (hosted, one instance per participant)
**AI client:** Claude Code

A self-paced tutorial on governing MCP integrations with Obot v0.26. The labs cover prompt injection, tool access, gateway data filtering, and monitoring and enforcement for local MCP servers.

Adapted from [Dev Summit Toronto](../dev_summit_toronto). This version retains the same exercises, commands, and lab sequence, with explanations written for an individual working through the tutorial at their own pace.

> In these labs, you'll apply controls outside the model: restricting which tools it can call, filtering the data returned through the gateway, and enforcing policy on your device. These controls limit what the integration permits even when the model follows malicious instructions.

## Labs

| Folder | Lab | You do | Control demonstrated |
|--------|-----|--------|----------------------|
| `00-prerequisites` | Setup | First login (detected email + set password) and confirm Claude Code | — |
| `01-connect-exploit` | Lab A — Connect & Exploit | Add the vulnerable MCP server, expose it As-Is through a vMCP, inspect a prompt-injection attempt, then trace the tool calls in the audit log | Visibility (gateway audit) |
| `02-contain-blast-radius` | Lab B — Contain the Blast Radius | Restrict the support tools with a Managed vMCP and repeat the request; test gateway filters with a separate sample-data server | Least privilege + data filtering |
| `03-audit-shadow-ai` | Lab C — Audit & Shadow AI | Enroll Obot Sentry, inventory your machine, forward *local* MCP logs, and enforce an allow-list | Fleet visibility + local enforcement |

## What changed vs the classic dev-summit

This scenario targets **Obot v0.26**, so it uses the current platform model:

- **Login** — Obot Academy provisions your account; you sign in with your **detected email** and set a password. No bootstrap token.
- **vMCPs, not composite servers** — clients connect through **Virtual MCPs (vMCPs)**. Lab A exposes the vulnerable server **As-Is** (all tools); Lab B rebuilds it as a **Managed** vMCP that curates the tool surface — the v0.26 replacement for the old composite-server model.

## Recommended Order

Run the sections in the order above. Each lab builds on the one before it.

The [top-level index](index.json) provides the combined tutorial: the prerequisites introduction, all 18 steps, and the final workshop recap. Each lab directory also contains an `index.json` with its own introduction, steps, and completion page. Those intermediate introductions and completion pages are only included when using the individual lab indexes.

For more details, visit the [Obot documentation](https://docs.obot.ai).
