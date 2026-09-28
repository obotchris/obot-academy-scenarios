# Block 3 Complete

You've extended auditing beyond the gateway: your machine now reports its AI-tooling inventory to Obot, forwards local MCP audit logs centrally, and enforces an allow list on the device.

## What You Learned

- How to install and enroll the Obot Sentry client (`obot-sentry`) using an enrollment key
- How to inventory local AI clients, MCP servers, and skills with `obot-sentry scan --submit`
- How to automate scanning with hooks (`sudo obot-sentry hook-install`)
- How to install a local MCP server and see its audit logs forwarded to Obot
- How to enforce policy on the device — blocking unapproved local MCP tool calls and allowing approved ones

## Next

Continue to **Block 4: Filtering Sensitive Data** to add a source catalog and use gateway filters to redact and block sensitive data — and learn why testing filters matters.
