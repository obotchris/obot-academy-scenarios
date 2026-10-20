# Keep It Current with Hooks

Running `obot-sentry scan --submit` by hand is fine for a one-off, but you don't want to rely on people remembering. **Hooks** run scans automatically as tooling changes.

## Install the Hooks

```bash
sudo obot-sentry hook-install
```{{copy}}

This runs with `sudo` because the hooks are installed at the system level.

## What the Hooks Do

- **Trigger scans automatically** — newly added AI clients, MCP servers, and skills are picked up without anyone remembering to scan
- **Respect the submission throttle** — results are still submitted at most once every 60 minutes, so frequent triggers don't flood the server
- **Keep the fleet inventory fresh** — the per-device, per-MCP-server, and per-skill views in Obot stay up to date

The hooks are removed as part of uninstalling `obot-sentry` (see the cleanup commands in the final step). With hooks installed, your machine now continuously reports its inventory back to Obot. Next you'll see the same client forward **local** MCP audit logs.
