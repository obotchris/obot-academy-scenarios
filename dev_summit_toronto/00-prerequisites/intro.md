# Governing Enterprise AI Agents — Prerequisites

Welcome to **Dev Summit Toronto**, running on **Obot v0.26**. Obot is an open-source platform for governing MCP (Model Context Protocol) technologies. This workshop is hands-on and security-focused: you'll attack a badly-governed AI integration, watch it succeed, then dismantle the attacker's options one control at a time.

## How the labs fit together

You will attack a badly-governed integration, watch it work, then take away the attacker's options one control at a time — and prove each control with the audit log.

| Lab | You do | Control demonstrated |
|-----|--------|----------------------|
| **Lab A — Connect & Exploit** | Add the vulnerable MCP server, expose it As-Is through a vMCP, run a live prompt-injection → PII → exfil attack, then read the audit trail | Visibility (gateway audit) |
| **Lab B — Contain the Blast Radius** | Rebuild the same integration with a least-privilege (Managed) vMCP + a gateway PII filter; re-run the attack | Least privilege + data filtering |
| **Lab C — Audit & Shadow AI** | Enroll Obot Sentry, inventory your machine, forward *local* MCP logs, and enforce an allow-list | Fleet visibility + local enforcement |

> **Golden rule of the day:** the model is not a security control. Every defense below sits *outside* the model — at the gateway, in the tool surface, or on the device.

## What's different on v0.26

- **Login** — Obot Academy provisions your account, so there is **no bootstrap token** to copy. You sign in with your **detected email** and set a password on first use. The first account becomes the **Owner**.
- **vMCPs, not composite servers** — clients connect through **Virtual MCPs (vMCPs)**, which control exactly which tools are exposed. Lab A exposes the vulnerable server **As-Is**; Lab B rebuilds it as a **Managed** vMCP that curates the tool surface.

## Prerequisites

- Claude Code installed, as the AI client for every lab (`obot-sentry` in Lab C also supports Codex, VS Code, and Cursor)
- A machine where you can install and enroll the Obot Sentry client (`obot-sentry`) in Lab C, with `sudo` access to install its hooks

A running Obot v0.26 instance is provided for you in this environment — you do not need to install or start anything.
