# Install and Enroll the Obot Sentry Client

**Obot Sentry** (`obot-sentry`) is a client that runs on your machine, takes an inventory of your AI tooling, and reports it back to your Obot instance.

Enrolling the client is driven from the Obot admin UI: you generate an enrollment key, download the install artifacts for your platform, then follow the installation instructions.

## Step 1: Generate an Enrollment Key

1. In the Obot admin UI, go to the client enrollment area under **Device Management / Devices / Configuration**
2. Click **Get Started**
3. Click **New Key** and then **Create Key**
> ⚠️ **The enrollment key is shown only once.** Copy it now and save it somewhere safe — you won't be able to view it again. You'll need it to enroll the client in the next step.
4. Select the **installation method** — for this workshop, choose **Do it yourself**
5. Select your **operating system**


## Step 2: Download the Install Artifacts

Download the install artifacts for your operating system from the dialog.

Extract the file using **tar -xvf <filename>**

## Step 3: Install and Enroll obot-sentry

Follow the installation instructions shown for your platform. They walk you through installing the `obot-sentry` client and enrolling it against your Obot instance using the enrollment key you saved. This connects your workstation to your Obot instance so its inventory rolls up centrally.
