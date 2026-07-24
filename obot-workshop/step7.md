# Scan and Report Your Inventory

Now that `obot-sentry` is enrolled, you can take an inventory of the AI tooling on your machine. A scan gives you — and, at the fleet level, your Obot admins — visibility into what's actually installed.

## Run a Scan

```bash
obot-sentry scan --submit
```

`--submit` sends the results to your Obot instance. By default, scans are submitted at most once every 60 minutes; runs within that window skip submission.

A scan reports:

- Every **AI client** it recognises (Claude Code, Claude Desktop, Cursor, VS Code, Codex, Goose, Windsurf, Zed, and more)
- The **MCP servers** each client is configured to talk to — including the `github-obot` gateway connection you added earlier
- Any **skills and plugins** present on disk

## Fleet Visibility in Obot

Because the client is enrolled against your Obot instance, submitted scans roll up into Obot for organisation-wide visibility. In the admin UI you can review inventory across devices — drilling into per-device scan history, seeing which MCP servers appear across users (collated by content hash), and which skills are installed where.

> This is how an organisation answers "what AI tools and MCP servers are running across our machines?" without manually surveying everyone.

## Cleanup (Optional)

To remove `obot-sentry` later — the binary, its configuration, and the device identity and scan state (macOS):

```bash
sudo rm -f /usr/local/bin/obot-sentry
sudo defaults delete /Library/Preferences/com.obot.obot-sentry
sudo rm -rf "/Library/Application Support/obot/obot-sentry"
rm -rf "$HOME/Library/Application Support/obot/obot-sentry" "$HOME/Library/Caches/obot/obot-sentry"
```
