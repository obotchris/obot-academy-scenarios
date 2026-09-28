# First Login & Owner Setup

In earlier versions, the first login required a one-time **bootstrap token**. On Obot Academy that step is **done for you** — your account is already provisioned against your **detected email**, and Obot's built-in **Local** auth provider is enabled. All you need to do is sign in and set a password.

## Open the Obot Admin UI

Open the Obot admin UI in your browser and go to the login page.

## Sign In and Set Your Password

1. Your **email address is already detected** and shown on the login screen — this is the identity your Obot activity is attributed to.
2. Because this is your **first sign-in**, Obot asks you to create a password. Enter your chosen password **twice** — once in **Password** and once in **Confirm Password** — then submit.
3. The **first account to sign in becomes the Owner** of the instance, so you land in the admin UI with full administrative rights.

> **Heads up:** if you're taken to the owner setup route (`/admin/setup`) instead of straight into the app, complete the password step there — it's the same flow. Once you've set your password you won't be prompted again; future sign-ins just use your email and password.

You now have an Obot v0.26 instance with yourself as the **Owner**. From here you can configure MCP servers, build vMCPs, and manage users and their roles under **User Management** once their accounts exist.
