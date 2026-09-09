# Connect the Custom Server to Claude Code

You've added the `pii-local` container as a hosted MCP server in Obot. Now connect it to Claude Code through the Obot gateway — the same way you connected the GitHub server — and make a tool call against it.

## Step 1: Get the Gateway Connection String

1. In Obot, under **MCP Servers** open the `pii-local` server.
2. Click **Connect to Server**
3. Copy the connection string shown in the dialog or click the button to add it to the clients that support that method.

## Step 2: Add the Server to Claude Code

Add `pii-local` as an HTTP MCP server in Claude Code, using the connection URL from the dialog:

```bash
claude mcp add --transport http "pii-local" "<connection URL from the Connect to Server dialog>"
```{{copy}}

You can verify that the server is now present in claude by typing the following command

```bash
claude mcp list
```{{copy}}

## Step 3: Make a Request

In a Claude Code session, send a prompt such as:

> get me a list of customers using pii-local

As with the GitHub server, the first time you do this you may be prompted to authenticate — click the Obot redirect link and complete the flow.

Claude will recognise that a tool provided by the `pii-local` server through Obot is the right one for the job and ask for your approval before calling it — click **Allow**.

The request is routed through the Obot gateway to the `pii-local` container, and Claude returns the customer records — names, email addresses, and other fields — from the PII demo data.

Each call goes through the Obot gateway, where it is authenticated, authorised, and logged. You'll review these entries in Block 3, and in Block 5 you'll apply gateway filters to redact and block this sensitive data.
