# First Login & Prerequisites

In earlier versions, the first login required a one-time **bootstrap token**. On Obot Academy that step is **done for you** — your account is already provisioned against your **detected email**, and Obot's built-in **Local** auth provider is enabled. All you need to do is sign in and set a password.

## Step 1: Sign In and Set Your Password

1. Open the Obot admin UI in your browser (URL from the environment panel) and go to the login page.
2. Your **email address is already detected** and shown on the login screen — this is the identity your Obot activity is attributed to.
3. Because this is your **first sign-in**, Obot asks you to create a password. Enter your chosen password **twice** — once in **Password** and once in **Confirm Password** — then submit.
4. The **first account to sign in becomes the Owner** of the instance, so you land in the admin UI with full administrative rights.

> **Heads up:** if you're taken to the owner setup route (`/admin/setup`) instead of straight into the app, complete the password step there — it's the same flow. Once you've set your password you won't be prompted again.

## Step 2: Confirm Claude Code

Confirm Claude Code is installed:

```bash
claude --version
```{{copy}}

And that you can list MCP servers (it may be empty for now):

```bash
claude mcp list
```{{copy}}

You now have an Obot v0.26 instance with yourself as the **Owner**, and Claude Code ready to connect. On to Lab A.
