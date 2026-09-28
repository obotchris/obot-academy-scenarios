# Block 1: Setting Up MCP Access

In this block you'll add the **GitHub** MCP server, then expose it to clients through a **Virtual MCP (vMCP)** — the v0.26 way of connecting through the Obot gateway. A vMCP aggregates one or more backing servers behind a single endpoint and controls **exactly which tools** are available.

You'll:

1. Generate Github PAT
2. Create a vMCP that exposes its tools
3. **Test the vMCP with Obot's built-in MCP inspector** — no external client required
4. Connect Claude Code to the vMCP and query your repositories
5. Add a custom **container** MCP server (the PII demo, used again in Block 4)
6. Create a second vMCP that **curates** the tools it exposes, and see the restriction in action

This block assumes you've completed the **Prerequisites** section and are logged in as the **Owner**.

> **What changed in v0.26:** clients no longer connect to individual MCP servers directly, and composite servers are gone. Everything is exposed through vMCPs, and you choose which tools each vMCP surfaces. Every call still flows through the Obot gateway, where it is authenticated, authorised, and logged — which you'll review in Block 2.
