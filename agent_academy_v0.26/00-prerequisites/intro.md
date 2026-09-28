# Agent Academy: Prerequisites

Welcome to **Agent Academy**, running on **Obot v0.26**. Obot is an open-source platform for governing MCP (Model Context Protocol) technologies. This course takes you from a fresh instance to a working, audited, and filtered AI-to-GitHub integration.

The course is split into four blocks, each with its own section:

1. **Setting Up MCP Access** — add the GitHub MCP server, expose it through a **Virtual MCP (vMCP)**, test it with the built-in **MCP inspector**, connect Claude Code through the Obot gateway, and curate exactly which tools each vMCP exposes
2. **Auditing (Gateway Traffic)** — review the audit log of calls that flow through the gateway
3. **Obot Sentry (Fleet & Local Activity)** — enroll the Obot Sentry client, inventory your machine, and forward local MCP audit logs to Obot
4. **Filtering Sensitive Data** — use gateway filters to redact and block sensitive data

Start here to review the prerequisites and complete the one-time first login. Each block that follows builds on the one before it.

## What's New in v0.26

If you've run an earlier version of this course, two things have changed:

- **Login** — Obot Academy provisions your account for you, so there is **no bootstrap token** to copy. You sign in with your **detected email** and set a password on first use. The first account becomes the **Owner**.
- **MCP access** — clients no longer connect to individual MCP servers directly. Instead you expose servers through **Virtual MCPs (vMCPs)**, which control exactly which tools are available. vMCPs replace the old composite-server model.

## Prerequisites

- A GitHub account with a **Personal Access Token** (used later by the GitHub MCP server to reach your repositories)
- Claude Code installed, as the AI client for the gateway, local MCP, and filtering steps (`obot-sentry` supports Claude Code, Codex, VS Code, and Cursor)
- A machine where you can install and enroll the Obot Sentry client (`obot-sentry`), with `sudo` access to install its hooks

A running Obot v0.26 instance is provided for you in this environment — you do not need to install or start anything.
