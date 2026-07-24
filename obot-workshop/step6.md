# Install and Set Up the Obot CLI

So far you've worked entirely in the browser. The **Obot CLI** brings Obot to your local machine — it connects your workstation to your Obot instance, installs Obot's skills into your AI agents, and can inventory what's installed.

Enrolling the CLI is driven from the Obot admin UI: you generate an enrollment key, download the install artifacts for your platform, then follow the installation instructions.

## Step 1: Generate an Enrollment Key

1. In the Obot admin UI, go to the CLI enrollment area
2. Click **Generate Enrollment Key**
3. Select the **installation method** — for this workshop, choose **Do it yourself**
4. Select your **operating system**

> ⚠️ **The enrollment key is shown only once.** Copy it now and save it somewhere safe — you won't be able to view it again. You'll need it to enroll the CLI in the next step.

## Step 2: Download the Install Artifacts

Download the install artifacts for your operating system from the dialog.

## Step 3: Install and Enroll the CLI

Follow the installation instructions shown for your platform. They walk you through installing the `obot` CLI and enrolling it against your Obot instance using the enrollment key you saved.

Enrolling the CLI will:

- Connect your workstation to your Obot instance
- Detect the coding agents installed on your machine (Claude Code, Cursor, VS Code, Codex, and others)
- Install Obot's bootstrap skills into those agents: `obot`, `obot-scan`, `obot-skills-search`, and `obot-skills-install`

## Step 4: Confirm It's Enrolled

Once installation completes, verify the CLI is connected:

```bash
obot setup status
```

You should see that the CLI is enrolled against your instance and which clients were configured.
