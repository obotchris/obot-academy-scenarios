# Create a GitHub OAuth App

GitHub authentication uses the OAuth 2.0 flow. First you need the callback URL from Obot, then you register an OAuth App on GitHub.

## Step 1: Get the Obot Callback URL

1. In the Obot admin UI, navigate to **User Management → Auth Providers**
2. Click **Configure** next to **GitHub**
3. Copy the **Callback URL** shown in the configuration dialog — you will need it in the next step

## Step 2: Register the OAuth App on GitHub

1. Go to [GitHub Settings → Developer settings → OAuth Apps](https://github.com/settings/developers)
2. Click **New OAuth App**
3. Fill in the fields:
   - **Application name** — e.g. `Obot`
   - **Homepage URL** — the URL of your Obot instance
   - **Authorization callback URL** — paste the Callback URL you copied from Obot
4. Click **Register application**
5. On the app page, click **Generate a new client secret**
6. Copy the **Client ID** and the newly generated **Client Secret** — keep them handy for the next step

> The Client Secret is only shown once. If you lose it, generate a new one.
