# Obot Workshop: GitHub Auth, MCP, and Audit End-to-End

Obot is an open-source platform for implementing MCP (Model Context Protocol) technologies. This workshop takes you through a complete, realistic flow from a fresh instance to a working, audited AI-to-GitHub integration.

You will:

1. Log in to Obot with the bootstrap token
2. Set up GitHub as an authentication provider and make yourself **Owner**
3. Add the GitHub MCP server and connect Claude to it through the Obot gateway
4. Ask Claude to list your GitHub repositories
5. Review the audit log to see the tool call that was made
6. Install the Obot CLI and connect it to your instance
7. Scan and report the AI-tooling inventory on your machine
8. Install a skill into Claude through Obot

By the end you will have seen how Obot authenticates users, hosts MCP servers, brokers AI tool calls, records everything for audit, and manages tooling and skills across your machines.

## Prerequisites

- A GitHub account (for auth, and to create an OAuth App and a Personal Access Token)
- Claude Desktop installed, to connect an AI client to the gateway
- Homebrew (or the ability to download a binary) to install the Obot CLI
- Optional: Claude Code, to install skills from inside the agent

A running Obot instance with authentication enabled is provided for you in this environment — you do not need to install or start anything.
