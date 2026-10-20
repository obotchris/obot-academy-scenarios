# Switch to Blocking & Why You Must Test Filters

A redaction filter sanitises a response. Sometimes you'd rather stop it entirely. And sometimes a filter you *thought* was working quietly lets data through — which is the most important lesson in this lab.

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

> ⚠️ **The lesson:** a filter you haven't tested is a filter you can't trust. Always validate against representative or synthetic data before relying on it. Filtering is a **backstop**; least privilege (step 1) is the **primary** control.

> ✅ **Lab B takeaway:** two independent controls — least privilege and gateway filtering — each defeat the Lab A attack, and neither depends on the model behaving.
