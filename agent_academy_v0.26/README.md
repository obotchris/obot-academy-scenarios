# Agent Academy (Obot v0.26)

An updated version of the Obot workshop for **Obot v0.26**, split into a prerequisites section plus four self-contained blocks. Each block is its own scenario (with its own `index.json`, `intro.md`, step files, and `finish.md`) and can be run on its own or in sequence.

This course reflects the v0.26 platform changes:

- **Login** — Obot Academy provisions your account and bypasses the one-time bootstrap token. Your **detected email** is used as your identity, and on first sign-in you set a password (entering it twice) with the built-in **Local** auth provider. The first account becomes the **Owner**.
- **MCP access** — MCP servers are now exposed to clients through **Virtual MCPs (vMCPs)**, which replace the old standalone-connection and composite-server models. A vMCP aggregates one or more backing servers and controls exactly which tools are exposed. You also test servers with the built-in **MCP inspector** before wiring up an external client.

## Sections

| Folder | Section | Covers |
|--------|---------|--------|
| `00-prerequisites` | Prerequisites & First Login | Prerequisites + local first-login (detected email, set password, become Owner) |
| `01-mcp-access` | Block 1: Setting Up MCP Access | Add the GitHub MCP server, build a vMCP, test it in the MCP inspector, connect Claude Code, add a custom container server, and curate tools with a vMCP |
| `02-auditing-gateway` | Block 2: Auditing — Gateway Traffic | View the gateway audit log |
| `03-auditing-fleet` | Block 3: Auditing — Fleet & Local Activity | Enroll Obot Sentry, scan, hooks, forward local MCP logs, enforce policy |
| `04-filters` | Block 4: Filtering Sensitive Data | Add a source catalog + gateway filters |

## Recommended Order

Run the sections in the order above. Each block's intro assumes the previous block is complete, and each finish points to the next block.

For more details, visit the [Obot documentation](https://docs.obot.ai).
