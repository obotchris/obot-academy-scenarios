# Install a Skill in Claude

Finally, use Obot to install a **skill** into Claude. Skills are reusable capabilities your organisation can publish through Obot and roll out to everyone's agents.

## Option A: From the Terminal

Search the catalog for a skill:

```bash
obot skills search "incident report"
```

Install one into your agents:

```bash
obot skills install incident-report
```

## Option B: From Inside Claude Code

Because `obot setup` installed Obot's bootstrap skills into Claude Code, you can do the same thing without leaving your agent. In a Claude Code session, run:

```
/obot-skills-search incident report
```

then install the one you want:

```
/obot-skills-install incident-report
```

## Verify

Start a new Claude session and confirm the skill is available — Claude will now be able to invoke it. You've gone full circle: from a fresh Obot instance to an authenticated, audited, tool-enabled AI client with organisation-managed skills.

> Skills installed this way are managed centrally in Obot, so updates and new skills can be pushed out to your whole team from one place.
