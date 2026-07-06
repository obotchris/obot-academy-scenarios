# Create a Google OAuth App

Google authentication uses the OAuth 2.0 flow. First grab the callback URL from Obot, then create an OAuth client in the Google Cloud Console.

## Step 1: Get the Obot Callback URL

1. In the Obot admin UI, navigate to **User Management → Auth Providers**
2. Click **Configure** next to **Google**
3. Copy the **Callback URL** shown in the configuration dialog — you will need it below

## Step 2: Create the OAuth Client in Google Cloud

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. In the left menu, go to **APIs & Services → OAuth consent screen**
4. Select **External** as the user type and click **Create**
5. Fill in the required fields (app name, support email, developer contact) and click **Save and Continue** through the remaining screens
6. Go to **APIs & Services → Credentials**
7. Click **Create Credentials → OAuth client ID**
8. Set the application type to **Web application**
9. Under **Authorised redirect URIs**, paste the Callback URL you copied from Obot
10. Click **Create**
11. Copy the **Client ID** and **Client Secret** from the confirmation dialog — keep them handy for the next step
