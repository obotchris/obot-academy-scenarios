# Lab C: Audit & Shadow AI

**Goal:** everything so far went *through the gateway*. But developers run MCP servers **locally**, straight into their client, never touching Obot. That's the shadow-AI blind spot. **Obot Sentry** (`obot-sentry`) closes it — first with visibility, then with enforcement.

In this lab you'll:

1. Enroll the Obot Sentry client on your machine
2. Inventory your AI tooling and roll it up to Obot
3. Keep the inventory current with hooks
4. Add a purely local MCP server and see its audit logs forwarded to Obot
5. Turn on local enforcement so only approved MCP servers can run

This lab assumes you've completed **Lab A** and **Lab B**.
