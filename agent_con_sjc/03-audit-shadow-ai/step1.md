# Enroll the Obot Sentry Client

**Obot Sentry** (`obot-sentry`) is a client that runs on your machine, takes an inventory of your AI tooling, and reports it back to your Obot instance. Enrollment is driven from the Obot admin UI.

## Step 1: Generate an Enrollment Key

1. In the Obot admin UI, go to **Device Management → Devices → Configuration** and click **Get Started**
2. Click **New Key → Create Key**
> ⚠️ The enrollment key is shown **once** — copy it now and save it somewhere safe.
3. Choose the install method **Do it yourself**, then select your **operating system**

## Step 2: Download and Extract the Install Artifacts

Download the install artifacts for your OS from the dialog, then extract them:

```bash
tar -xvf <downloaded-file>
```{{copy}}

## Step 3: Install and Enroll obot-sentry

Follow the on-screen install/enroll instructions to install `obot-sentry` and enroll it against your Obot instance using the key you saved. (Installing hooks later requires `sudo`.) This connects your workstation to your Obot instance so its inventory rolls up centrally.
