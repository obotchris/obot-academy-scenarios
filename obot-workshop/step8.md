# Automate Scanning with Hooks

Running `obot-sentry scan --submit` by hand is fine for a one-off, but you don't want to rely on people remembering to do it. **Hooks** let `obot-sentry` run scans automatically, so your inventory stays current on its own.

## Install the Hooks

```bash
sudo obot-sentry hook-install
```

This is run with `sudo` because the hooks are installed at the system level.

## What the Hooks Do

Once installed, the hooks:

- **Trigger scans automatically** — instead of relying on a manual `obot-sentry scan`, a scan runs on its own, so newly added AI clients, MCP servers, and skills are picked up without anyone remembering to run it.
- **Respect the submission throttle** — as with a manual run, results are submitted to your Obot instance at most once every 60 minutes, so frequent triggers don't flood the server.
- **Keep the fleet inventory fresh** — because scans keep flowing in, the per-device, per-MCP-server, and per-skill views in the Obot admin UI stay up to date, which is what makes fleet-wide visibility reliable.

## Removing the Hooks

The hooks are removed as part of uninstalling `obot-sentry` (see the cleanup commands in the previous step).

You've now gone full circle: from a fresh Obot instance to an authenticated, audited, tool-enabled AI client, with an enrolled machine that continuously reports its AI-tooling inventory back to Obot.
