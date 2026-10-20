# Congratulations — Workshop Complete!

You attacked a badly-governed AI integration, then dismantled the attacker's options one control at a time — and proved each control with the audit log.

## Wrap-up — map the attack to the controls

| Lab A attack step | Control that stops it | Where it lives |
|-------------------|-----------------------|----------------|
| Poisoned ticket text hijacks the agent | You can't stop untrusted content — so remove what it can reach | design |
| Agent reads PII (`get_customer` / `list_customers`) | Managed vMCP drops the tool (B1); gateway filter redacts/blocks fields (B3–B5) | tool surface / gateway |
| Agent exfiltrates (`send_webhook`) | Managed vMCP drops the egress tool (B1) | tool surface |
| Poisoned tool *description* | Approved source catalog / registry review (A6, B3) | registry |
| Local, off-gateway MCP call | Sentry forwarding + local enforcement (C4–C5) | device |
| Everything | Gateway + Sentry audit log (A7, C4) | audit |

**One sentence to leave with:** don't try to make the model perfectly obedient — remove the capabilities an attacker needs, filter what leaves, and log everything, everywhere.

## Optional extension labs (self-paced)

- **GitHub MCP + gateway audit** — add the GitHub MCP server, query your repos from Claude Code, and see the calls in the audit log.
- **Add another auth provider** (Google) and manage user roles.
- **Add a model provider** and build an Obot agent that combines a model with a least-privilege tool set.
- **Token & spend visibility** — review per-user / per-group usage in Obot.

For more details, visit the [Obot documentation](https://docs.obot.ai).
