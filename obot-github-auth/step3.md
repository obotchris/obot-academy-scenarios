# Configure GitHub Auth in Obot

Now feed the GitHub credentials back into Obot.

1. Return to the Obot **User Management → Auth Providers** page
2. Click **Configure** next to **GitHub**
3. Enter the **Client ID** and **Client Secret** you copied from GitHub
4. Optionally set **Email Domains** to restrict access (e.g. `example.com`), or use `*` to allow any email domain
5. Click **Confirm**

The GitHub auth provider is now enabled. The login page will offer a **Sign in with GitHub** button.

> **Email Domains** are a simple allow-list. Only users whose GitHub account email matches one of the listed domains will be able to sign in. Use `*` while testing, then tighten it for production.
