# Enforce Policy at the Local Level

Forwarding audit logs gives you **visibility** into local MCP activity. `obot-sentry` can go a step further and **enforce** policy on the machine itself — blocking tool calls that aren't explicitly allowed, before they run.

In this step you'll turn on tool-call enforcement, watch the local filesystem MCP call from the previous step get **blocked**, then add an allow rule so it succeeds again.

## Step 1: Enable Tool Call Enforcement

1. In the Obot admin UI, go to **Device Management / Devices / Configuration**
2. Turn on **tool call enforcement**
3. Leave the settings at their **default** and save the configuration

With enforcement on and no servers explicitly allowed, local MCP tool calls are blocked by default.

## Step 2: Run the Same Request and See It Blocked

In a Claude Code session started from the folder you configured earlier, send the same prompt you used before:

> List the files in this folder using filesystem mcp

**Remember to specify *using the filesystem mcp*** so Claude forces an MCP call rather than a standard file read.

This time the call is **blocked** — `obot-sentry` enforces the policy on the machine, so the filesystem MCP server is not allowed to run and no files come back.

## Step 3: Confirm the Block in Obot

Return to the Obot admin UI and open the **enforcement decisions** view.

The attempted filesystem MCP call is listed as **blocked** — you can see the enforcement decision that stopped it, alongside the device and user it came from.

## Step 4: Add an Allowed MCP Server

Now allow the filesystem server explicitly:

1. Back in **Device Management / Devices / Configuration**, scroll to the bottom and add an **allowed MCP server**
2. Set the **registry** to **NPM**
3. Set the **package name** to:

```
@modelcontextprotocol/server-filesystem
```{{copy}}

4. Click **Save**

## Step 5: Run the Request Again and See the Files

Send the same prompt one more time:

> List the files in this folder using filesystem mcp

Because the filesystem server is now on the allow list, enforcement lets the call through and Claude returns the files in the folder.

## Why This Matters

Visibility tells you what happened; enforcement lets you control what's allowed to happen. With `obot-sentry` enforcing an allow list on the device, you can permit only approved MCP servers to run locally — turning your fleet inventory from a report into a control.
