# Create a Redaction Filter

Because MCP traffic flows through the Obot gateway, Obot can inspect responses and strip sensitive fields before they reach the client — no change to the underlying server required.

## Create the Filter

1. In the Obot admin UI, go to **MCP Management → Filters** and click **Add New Filter**
2. Base it on the **built-in** filter (it detects names, emails, and US driver's licences)
3. Set the action to **Redact** and the target field to **email addresses**
4. Set **Server to apply to** = **`customer-demo-data`**
5. **Save**

## Verify the Redaction

Run the same request again:

> List the data from the customer-demo-data server.

This time the **email addresses are redacted**, while names and licence numbers still come through. The filtering is happening **at the gateway**, not in the client — the client never receives the sensitive values.

> This is the "let the call through, but sanitise it" pattern: useful when an agent legitimately needs a tool but shouldn't see every field it returns.
