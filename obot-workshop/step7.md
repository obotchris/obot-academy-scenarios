# Scan and Report Your Inventory

Now that the CLI is connected, you can take an inventory of the AI tooling on your machine. `obot scan` gives you — and, at the fleet level, your Obot admins — visibility into what's actually installed.

## Run a Scan

```bash
obot scan
```

`obot scan` walks your home directory and reports:

- Every **AI client** it recognises (Claude Code, Claude Desktop, Cursor, VS Code, Codex, Goose, Windsurf, Zed, and more)
- The **MCP servers** each client is configured to talk to — including the `github-obot` gateway connection you added earlier
- Any **skills and plugins** present on disk

## Read the Report

The output groups results by client, so you can see, for example, that Claude Desktop is pointed at your Obot gateway and which MCP servers are reachable through it.

## Fleet Visibility in Obot

Because the CLI is connected to your Obot instance, scan results roll up into Obot for organisation-wide visibility. In the admin UI you can review inventory across devices — drilling into per-device scan history, seeing which MCP servers appear across users (collated by content hash), and which skills are installed where.

> This is how an organisation answers "what AI tools and MCP servers are running across our machines?" without manually surveying everyone.
