# Switch to Blocking & Why You Must Test Filters

You've seen how redaction removes matching values while allowing the rest of a response through. Next, you'll switch the filter to blocking and compare the result. You'll then test a driver's licence rule against the sample records to see whether it recognises every format they contain.

## Step 1: Switch to Blocking

1. Edit the filter and change the action from **Redact** to **Block** (still on email addresses)
2. **Save**, then re-run:

> List the data from the customer-demo-data server.

Because a matching record is blocked outright, **nothing comes back** — the response is stopped rather than redacted.

## Step 2: Test a Different Rule — and Watch It Leak

1. Undo the block (set the action back to **Redact**)
2. Change the rule to redact on **US driver's licence** instead of email
3. **Save** and re-run:

> List the data from the customer-demo-data server.

This time **some licence numbers still leak through**. The built-in rule doesn't match every state's format (e.g. the 9-character Florida-style value), so those records slip past unredacted.

> **Lab B recap:** tool restrictions and data filters address different parts of the integration. The Managed vMCP removed tools the support agent didn't need. The filtering exercise showed how to redact or block sensitive data when a tool must remain available, and how unmatched values can still pass through. Test your rules against representative or synthetic records before relying on them to protect those fields.
