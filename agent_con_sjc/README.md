# Dev Summit Toronto — Governing Enterprise AI Agents

**Workshop:** Governing Enterprise AI Agents with Obot — Tools, Exploits & Prompt Injection
**Platform:** Obot v0.26 (hosted, one instance per participant)
**AI client:** Claude Code

A security-focused walkthrough built on **Obot v0.26**. You attack a badly-governed integration, watch it work, then take away the attacker's options one control at a time — and prove each control with the audit log.

> **Golden rule of the day:** the model is not a security control. Every defense here sits *outside* the model — at the gateway, in the tool surface, or on the device.

## Labs

| Folder | Lab | You do | Control demonstrated |
|--------|-----|--------|----------------------|
| `00-prerequisites` | Setup | First login (detected email + set password) and confirm Claude Code | — |
| `01-connect-exploit` | Lab A — Connect & Exploit | Add the vulnerable MCP server, expose it As-Is through a vMCP, run a live prompt-injection → PII → exfil attack, then read the audit trail | Visibility (gateway audit) |
| `02-contain-blast-radius` | Lab B — Contain the Blast Radius | Rebuild the integration with a least-privilege (Managed) vMCP + a gateway PII filter; re-run the attack | Least privilege + data filtering |
| `03-audit-shadow-ai` | Lab C — Audit & Shadow AI | Enroll Obot Sentry, inventory your machine, forward *local* MCP logs, and enforce an allow-list | Fleet visibility + local enforcement |

## What changed vs the classic dev-summit

This scenario targets **Obot v0.26**, so it uses the current platform model:

- **Login** — Obot Academy provisions your account; you sign in with your **detected email** and set a password. No bootstrap token.
- **vMCPs, not composite servers** — clients connect through **Virtual MCPs (vMCPs)**. Lab A exposes the vulnerable server **As-Is** (all tools); Lab B rebuilds it as a **Managed** vMCP that curates the tool surface — the v0.26 replacement for the old composite-server model.

## Recommended Order

Run the sections in the order above. Each lab builds on the one before it.

For more details, visit the [Obot documentation](https://docs.obot.ai).
