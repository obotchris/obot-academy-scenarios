# Block 5: Filtering Sensitive Data

Because MCP traffic flows through the Obot gateway, Obot can inspect responses and **redact** or **block** sensitive data before it ever reaches the client.

In this final block you'll first add a **source catalog** — a Git repository that defines additional MCP servers your organisation wants to make available. That catalog includes a `synthetic-pii` server that returns fake records (names, email addresses, and US driving licence numbers) — safe test data for exercising filters. You'll then create gateway filters against it and see why **testing** a filter matters.

By the end you'll have seen filters redact data, block responses outright, and — importantly — leak data when a rule doesn't match, driving home why filters must be validated before you rely on them.
