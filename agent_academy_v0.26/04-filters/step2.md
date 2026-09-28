# Filter Sensitive Data with Gateway Filters

Because MCP traffic flows through the Obot gateway, Obot can inspect responses and **redact** or **block** sensitive data before it ever reaches the client. In this step you'll use the `customer-demo-data` server from the catalog you added in the previous step to see filters in action — and why testing them matters.

The `customer-demo-data` server returns fake records containing **names, email addresses, and US driving licence numbers** — safe test data for exercising filters.

## Step 1: Add the Server and Expose It Through a vMCP

1. In the Obot catalog, find **`customer-demo-data`** (from the `academy-catalog` source you added earlier) and add it as an MCP server
2. Go to **vMCPs → Create vMCP**, drag `customer-demo-data` onto the canvas, name it `customer-demo-data`, and click **Create**
3. Open the vMCP and click **Connect**, then copy the **Connection URL** (it looks like `https://<your-instance>.obotacademy.net/mcp-connect/<vmcp-id>`)
4. Add it to Claude Code as an HTTP MCP server:

```bash
claude mcp add --transport http "Customer Demo Data" "<connection URL from the Connect dialog>"
```{{copy}}

> Prefer to skip the client? You can run every request in this step from the built-in **MCP inspector** instead — open the vMCP, click **Test vMCP**, and invoke the data tool there. The filter behaviour is identical because both paths go through the gateway.

## Step 2: List the Data (No Filter Yet)

In a Claude Code session, ask the server for its data:

> List the data from the customer-demo-data server

**You may be required to authenticate again.** The records come back in full — names, **email addresses**, and driving licence numbers all visible. This is the baseline.

## Step 3: Create a Redaction Filter

1. In the Obot admin UI, go to **MCP Management → Filters**
2. Click **Add New Filter** and base it on the **built-in** filter (it can detect names, email addresses, and US driving licence numbers)
3. Set the action to **Redact** for **email addresses**
4. Set the **server to apply it to** to **`customer-demo-data`**
5. **Save** the filter

## Step 4: Verify the Redaction

Run the same request again:

> List the data from the customer-demo-data server

This time the **email addresses are redacted**, while names and licence numbers still come through. The filter is being applied at the gateway.

## Step 5: Switch to Blocking

1. Edit the filter and change the action from **Redact** to **Block** (still on email addresses)
2. **Save**
3. Run the request again

Because a matching record is blocked outright, **nothing comes back** — the response is stopped rather than redacted.

## Step 6: Test a Different Rule — and Why Testing Matters

1. Undo the block (set the action back to **Redact**)
2. Change the filter to redact on **US driving licence** instead of email
3. **Save** and run the request again

This time **some of the licence data still leaks through** — the built-in rule doesn't catch every format in the data.

> **This is the important lesson:** filters are powerful, but a filter you haven't tested is a filter you can't trust. Always validate a filter against representative (or synthetic) data — the **MCP inspector** is a quick way to do this — before relying on it to protect real information.
