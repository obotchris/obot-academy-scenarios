# Inventory Your Machine

Now that `obot-sentry` is enrolled, take an inventory of the AI tooling on your machine.

## Run a Scan

```bash
obot-sentry scan --submit
```{{copy}}

`--submit` rolls the results up to Obot (throttled to once per 60 minutes; runs within that window skip submission). A scan reports:

- Every AI **client** it recognises (Claude Code, Codex, VS Code, Cursor)
- The **MCP servers** each client is configured to use — including the gateway connections you added in Labs A and B
- Any **skills and plugins** present on disk

## View It in Obot

Navigate to **Device Management → Devices → Overview** (widen the time window to the last hour if it's empty). Drill into the tabs to see per-device detail — per-device scan history, which MCP servers appear across users (collated by content hash), and which skills are installed where.

> This is how an organisation answers "what AI tools and MCP servers are running across our machines?" without manually surveying everyone.
