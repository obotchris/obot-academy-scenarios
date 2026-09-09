# Obot Dev Summit: Prerequisites

Welcome to the Obot Dev Summit course. Obot is an open-source platform for implementing MCP (Model Context Protocol) technologies. This course takes you from a fresh instance to a working, audited, and filtered AI-to-GitHub integration.

The course is split into five blocks, each with its own section:

1. **Setting Up Authentication** — configure GitHub as an auth provider and make yourself Owner
2. **Setting Up MCP Access** — add the GitHub MCP server and connect Claude Code through the Obot gateway
3. **Auditing (Gateway Traffic)** — review the audit log of calls that flow through the gateway
4. **Obot Sentry (Fleet & Local Activity)** — enroll the Obot Sentry client, inventory your machine, and forward local MCP audit logs to Obot
5. **Filtering Sensitive Data** — use gateway filters to redact and block sensitive data

Start here to review the prerequisites and complete the one-time bootstrap login. Each block that follows builds on the one before it.

## Prerequisites

- A GitHub account (for auth, and to create an OAuth App and a Personal Access Token)
- Claude Code installed, as the AI client for the gateway, local MCP, and filtering steps (`obot-sentry` supports Claude Code, Codex, VS Code, and Cursor)
- A machine where you can install and enroll the Obot Sentry client (`obot-sentry`), with `sudo` access to install its hooks

A running Obot instance with authentication enabled is provided for you in this environment — you do not need to install or start anything.
