# Break the Trifecta with a Least-Privilege vMCP

A support agent needs to *read tickets* and *search the KB*. It does **not** need to bulk-list customers, read raw PII, or post to arbitrary webhooks. So build a new vMCP that exposes **only** what's needed — the v0.26 replacement for the old composite (least-privilege) server.

## Create a Managed vMCP

1. In the Obot admin UI, go to **All Resources → vMCPs** and click **Create vMCP**
2. Choose the **vuln-support** entry and drag it onto the **+CREATE NEW VMCP** target in the centre
3. Give it a name and click **Create**:

```
support-safe
```{{copy}}

4. On the next screen, supply any required configuration, drop down the endpoint path and select **Default**, then click **Next**
5. When offered **As-Is** or **Managed**, choose **Managed** — this lets you curate exactly which tools are exposed

## Turn Off the Dangerous Tools

In the `support-safe` tool list, **turn OFF**:

- `send_webhook` — *removes the exfil path*
- `list_customers` — *removes bulk PII read*
- `reconcile_account` — *removes the poisoned-description tool*
- `get_customer` — *a summarizer doesn't need raw PII; keep it off for this agent*

Leave **ON**:

- `get_support_ticket`
- `search_kb`

Then **Save**.

> 🧠 **Debrief:** this is the most durable control in the room. You didn't try to *detect* the attack — you removed the capabilities it depended on. The backing `vuln-support` server can still do all of these things, but `support-safe` simply doesn't expose them. **Least privilege beats detection.**
