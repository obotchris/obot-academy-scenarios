# Block 4: Auditing — Fleet & Local Activity

Block 3 audited MCP calls that flow **through the gateway**. But developers also run MCP servers **locally** — configured straight into their AI client, running on their own machine, never touching the gateway. Normally that activity is a blind spot.

In this block you'll close that gap with **Obot Sentry** (`obot-sentry`) — a client that runs on your machine, takes an inventory of your AI tooling, and reports it back to your Obot instance. You'll:

1. Install and enroll the Obot Sentry client
2. Scan and report your machine's AI-tooling inventory
3. Automate scanning with hooks so inventory stays current
4. Install a local MCP server and see its audit logs forwarded to Obot

By the end you'll have the same visibility for **local** MCP servers as you have for gateway-hosted ones, rolled up centrally in Obot.
