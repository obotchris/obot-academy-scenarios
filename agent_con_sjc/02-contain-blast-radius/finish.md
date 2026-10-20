# Lab B Complete

You rebuilt the vulnerable integration so the Lab A attack can't happen — first by shrinking the tool surface with a Managed vMCP, then by filtering sensitive data at the gateway.

## What You Learned

- How to build a **Managed vMCP** that exposes only the tools an agent needs — removing the exfil path and the PII reads the attack depended on
- Why **least privilege beats detection**: you removed capabilities instead of trying to spot the attack
- How to add a **source catalog** of approved servers
- How to create gateway **redaction** and **blocking** filters, applied per server
- Why you must **test filters** — the built-in licence rule leaks formats it doesn't recognise

## Next

Continue to **Lab C: Audit & Shadow AI** — everything so far went *through the gateway*, but developers run MCP servers **locally**, straight into their client, never touching Obot. That's the shadow-AI blind spot. Obot Sentry closes it — first with visibility, then with enforcement.
