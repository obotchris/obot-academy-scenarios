# From Visibility to Control — Local Enforcement

Forwarding audit logs gives you **visibility** into local MCP activity. Sentry can go further and **enforce** policy on the machine itself — blocking tool calls that aren't explicitly allowed, before they run.

## Step 1: Enable Tool Call Enforcement

1. In the Obot admin UI, go to **Device Management → Devices → Configuration**, turn on **tool call enforcement**, keep the defaults, and save
2. Enforce on the device:

```bash
sudo obot-sentry hook-install --enforce
sudo defaults write /Library/Preferences/com.obot.obot-sentry EnforcementEnabled -bool true
```{{copy}}

*(macOS shown; use the command for your OS from the UI.)* With enforcement on and nothing allow-listed, local MCP calls are denied by default.

## Step 2: Re-run the Request and See It Blocked

In a Claude Code session started from the folder you configured earlier:

> List the files in this folder using the filesystem mcp.

The call is **blocked** — enforcement denies it on the device. Confirm it in Obot's **enforcement decisions** view, where the blocked attempt is listed alongside the device and user it came from.

## Step 3: Allow the Server Explicitly

1. Back in **Device Management → Devices → Configuration**, scroll to the bottom and add an **allowed MCP server**
2. Set the **registry** to **NPM** and the **package name** to:

```
@modelcontextprotocol/server-filesystem
```{{copy}}

3. **Save**

## Step 4: Re-run and See It Succeed

> List the files in this folder using the filesystem mcp.

Because the filesystem server is now on the allow list, enforcement lets the call through and Claude returns the files.

> ✅ **Lab C takeaway:** Sentry turns an inventory report into a control. You can permit only approved MCP servers to run locally — even ones that never touch the gateway.

## Cleanup (Optional, macOS)

```bash
sudo rm -f /usr/local/bin/obot-sentry
sudo defaults delete /Library/Preferences/com.obot.obot-sentry
sudo rm -rf "/Library/Application Support/obot/obot-sentry"
rm -rf "$HOME/Library/Application Support/obot/obot-sentry" "$HOME/Library/Caches/obot/obot-sentry"
```{{copy}}
