# Set Yourself as Owner

New users who sign in through an auth provider start with a basic role. To administer Obot, promote your GitHub account to **Owner**.

1. Log out of the bootstrap session
2. On the login page, click **Sign in with GitHub** and authenticate with your GitHub account
3. Log out again
4. Log back in using the **bootstrap token** (as you did earlier)
5. Navigate to **User Management → Users**
6. Find your GitHub account in the list and click **Update Role**, setting it to **Owner**

Log out of the bootstrap session one last time and sign back in with GitHub. You now have full admin rights on a GitHub-authenticated Obot instance.

> Signing in with GitHub once (step 2 above) is what creates your user record in Obot — you can only assign a role to a user that already exists.
