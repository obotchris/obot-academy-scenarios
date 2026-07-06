# Configure Google Auth in Obot

Now feed the Google credentials back into Obot.

1. Return to the Obot **User Management → Auth Providers** page
2. Click **Configure** next to **Google**
3. Enter the **Client ID** and **Client Secret** you copied from the Google Cloud Console
4. Optionally set **Email Domains** to restrict access (e.g. `example.com`), or use `*` to allow any email domain
5. Click **Confirm**

The Google auth provider is now enabled. The login page will offer a **Sign in with Google** button.

> **Email Domains** are a simple allow-list. This is especially handy with Google Workspace — set it to your company domain so only employees can sign in. Use `*` while testing.
