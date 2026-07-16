# Install and Set Up the Obot CLI

So far you've worked entirely in the browser. The **Obot CLI** brings Obot to your local machine — it connects your workstation to your Obot instance, installs Obot's skills into your AI agents, and can inventory what's installed.

## Step 1: Install the CLI

On macOS or Linux with Homebrew:

```bash
brew install obot-platform/tap/obot
```

Alternatively, download the binary for your platform from the [Obot releases page](https://github.com/obot-platform/obot/releases) and put it on your `PATH`.

Verify it's installed:

```bash
obot --version
```

## Step 2: Connect the CLI to Your Obot Instance

Run `obot setup`, pointing it at the URL of the Obot instance you've been using:

```bash
obot setup --url <your Obot instance URL>
```

`obot setup` will:

- Walk you through an **OAuth login** against your Obot instance (using the GitHub auth you configured earlier)
- Detect the coding agents installed on your machine (Claude Code, Cursor, VS Code, Codex, and others)
- Install Obot's bootstrap skills into those agents: `obot`, `obot-scan`, `obot-skills-search`, and `obot-skills-install`

Useful variations:

- `obot setup --url <url> --clients claude-code` — only set up Claude Code
- `obot setup --url <url> --clients none` — configure the CLI only, don't touch any agents

## Step 3: Confirm Setup

```bash
obot setup status
```

You should see that the CLI is authenticated against your instance and which clients were configured.
