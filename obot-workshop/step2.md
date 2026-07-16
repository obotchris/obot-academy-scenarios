# Set Up GitHub Authentication

Now configure GitHub as an authentication provider so users can sign in with their GitHub account. This uses the OAuth 2.0 flow.

## Step 1: Get the Obot Callback URL

1. In the Obot admin UI, navigate to **User Management → Auth Providers**
2. Click **Configure** next to **GitHub**
3. Copy the **Callback URL** shown in the configuration dialog

## Step 2: Register the OAuth App on GitHub

1. Go to [GitHub Settings → Developer settings → OAuth Apps](https://github.com/settings/developers)
2. Click **New OAuth App**
3. Fill in the fields:
   - **Application name** — e.g. `Obot`
   - **Homepage URL** — the URL of your Obot instance
   - **Authorization callback URL** — paste the Callback URL you copied from Obot
4. Click **Register application**
5. Click **Generate a new client secret**
6. Copy the **Client ID** and the new **Client Secret** (the secret is shown only once)

## Step 3: Configure GitHub Auth in Obot

1. Return to the Obot **Auth Providers** page and click **Configure** next to **GitHub**
2. Enter the **Client ID** and **Client Secret**
3. Optionally set **Email Domains** to restrict access (e.g. `example.com`), or use `*` to allow any domain
4. Click **Confirm**

## Step 4: Sign In and Set Yourself as Owner

The first user to log in needs to be set as **Owner**.

1. Log out of the bootstrap session
2. Click **Sign in with GitHub** and authenticate with your GitHub account
3. When prompted, set yourself as **Owner**

You now have a GitHub-authenticated Obot instance with yourself as the administrator. Anyone with a valid email can now log in; you can manage their roles in the **Users** section once their accounts exist.
