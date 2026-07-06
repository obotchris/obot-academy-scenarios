# Set Yourself as Owner

New users who sign in through an auth provider start with a basic role. To administer Obot, promote your Google account to **Owner**.

1. Log out of the bootstrap session
2. On the login page, click **Sign in with Google** and authenticate with your Google account
3. Log out again
4. Log back in using the **bootstrap token** (as you did earlier)
5. Navigate to **User Management → Users**
6. Find your Google account in the list and click **Update Role**, setting it to **Owner**

Log out of the bootstrap session one last time and sign back in with Google. You now have full admin rights on a Google-authenticated Obot instance.

> Signing in with Google once (step 2 above) is what creates your user record in Obot — you can only assign a role to a user that already exists.
