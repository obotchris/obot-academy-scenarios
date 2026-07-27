# Obot Workshop: GitHub Auth, MCP, and Audit End-to-End

Obot is an open-source platform for implementing MCP (Model Context Protocol) technologies. This workshop takes you through a complete, realistic flow from a fresh instance to a working, audited AI-to-GitHub integration.

You will:

1. Log in to Obot with the bootstrap token
2. Set up GitHub as an authentication provider and make yourself **Owner**
3. Add the GitHub MCP server and connect Claude Code to it through the Obot gateway
4. Ask Claude Code to list your GitHub repositories
5. Review the audit log to see the tool call that was made
6. Add a source catalog of MCP servers from a Git repository
7. Install and enroll the Obot Sentry client on your machine
8. Scan and report the AI-tooling inventory on your machine
9. Automate scanning with hooks so inventory stays current
10. Install a local MCP server and see its audit logs forwarded to Obot
11. Filter sensitive data with gateway filters — and learn why testing them matters

By the end you will have seen how Obot authenticates users, hosts MCP servers, brokers AI tool calls, records everything for audit, keeps an inventory of AI tooling across your machines, forwards audit logs from local MCP servers back to the server, and filters sensitive data at the gateway.

## Prerequisites

- A GitHub account (for auth, and to create an OAuth App and a Personal Access Token)
- Claude Code installed, as the AI client for the gateway, local MCP, and filtering steps (`obot-sentry` supports Claude Code, Codex, VS Code, and Cursor)
- A machine where you can install and enroll the Obot Sentry client (`obot-sentry`), with `sudo` access to install its hooks

A running Obot instance with authentication enabled is provided for you in this environment — you do not need to install or start anything.
