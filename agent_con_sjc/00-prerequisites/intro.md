# Governing Enterprise AI Agents — Prerequisites

This tutorial uses **Obot v0.26**, an open-source platform for governing MCP (Model Context Protocol) technologies. You'll connect a deliberately vulnerable customer-support integration, examine how prompt injection can misuse its tools, and apply controls that limit access to tools and data.

## How the labs fit together

Complete the labs in order. Lab A establishes the integration and its audit trail. Lab B uses that setup to test tool restrictions, then introduces data filtering. Lab C extends your work to MCP servers running locally on your machine.

| Lab | You do | Control demonstrated |
|-----|--------|----------------------|
| **Lab A — Connect & Exploit** | Add the vulnerable MCP server, expose it As-Is through a vMCP, run a live prompt-injection → PII → exfil attack, then read the audit trail | Visibility (gateway audit) |
| **Lab B — Contain the Blast Radius** | Rebuild the same integration with a least-privilege (Managed) vMCP + a gateway PII filter; re-run the attack | Least privilege + data filtering |
| **Lab C — Audit & Shadow AI** | Enroll Obot Sentry, inventory your machine, forward *local* MCP logs, and enforce an allow-list | Fleet visibility + local enforcement |

> In these labs, you'll apply controls outside the model: restricting which tools it can call, filtering the data returned through the gateway, and enforcing policy on your device. These controls limit what the integration permits even when the model follows malicious instructions.

## What's different on v0.26

- **Login** — Obot Academy provisions your account, so there is **no bootstrap token** to copy. You sign in with your **detected email** and set a password on first use. The first account becomes the **Owner**.
- **vMCPs, not composite servers** — clients connect through **Virtual MCPs (vMCPs)**, which control exactly which tools are exposed. Lab A exposes the vulnerable server **As-Is**; Lab B rebuilds it as a **Managed** vMCP that curates the tool surface.

## Prerequisites

- Claude Code installed, as the AI client for every lab (`obot-sentry` in Lab C also supports Codex, VS Code, and Cursor)
- A machine where you can install and enroll the Obot Sentry client (`obot-sentry`) in Lab C, with `sudo` access to install its hooks

A running Obot v0.26 instance is provided for you in this environment — you do not need to install or start anything.
