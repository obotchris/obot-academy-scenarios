# Congratulations — Workshop Complete!

You've completed the gateway and local-device exercises. The table below connects the risks you examined with the controls and audit records used throughout the tutorial.

## Wrap-up — map the attack to the controls

| Lab A attack step | Control that stops it | Where it lives |
|-------------------|-----------------------|----------------|
| Poisoned ticket text hijacks the agent | You can't stop untrusted content — so remove what it can reach | design |
| Agent reads PII (`get_customer` / `list_customers`) | Managed vMCP drops the tool (B1); gateway filter redacts/blocks fields (B3–B5) | tool surface / gateway |
| Agent exfiltrates (`send_webhook`) | Managed vMCP drops the egress tool (B1) | tool surface |
| Poisoned tool *description* | Approved source catalog / registry review (A6, B3) | registry |
| Local, off-gateway MCP call | Sentry forwarding + local enforcement (C4–C5) | device |
| Everything | Gateway + Sentry audit log (A7, C4) | audit |

Across these labs, you've explored how tool restrictions, data filters, and audit logs work together. Restricting tools limits the actions available to an agent, filtering controls which data reaches the client, and logging helps you inspect what happened. These controls let you govern the integration without relying entirely on the model to reject malicious instructions.

## Optional extension labs (self-paced)

- **GitHub MCP + gateway audit** — add the GitHub MCP server, query your repos from Claude Code, and see the calls in the audit log.
- **Add another auth provider** (Google) and manage user roles.
- **Add a model provider** and build an Obot agent that combines a model with a least-privilege tool set.
- **Token & spend visibility** — review per-user / per-group usage in Obot.

For more details, visit the [Obot documentation](https://docs.obot.ai).
