# Obot Dev Summit

A version of the Obot workshop split into a prerequisites section plus five self-contained blocks. Each block is its own scenario (with its own `index.json`, `intro.md`, step files, and `finish.md`) and can be run on its own or in sequence.

## Sections

| Folder | Section | Covers (from the original workshop) |
|--------|---------|-------------------------------------|
| `00-prerequisites` | Prerequisites & Bootstrap Login | Prerequisites + bootstrap token login |
| `01-authentication` | Block 1: Setting Up Authentication | GitHub OAuth auth provider + set Owner |
| `02-mcp-access` | Block 2: Setting Up MCP Access | Add GitHub MCP server + query repositories |
| `03-auditing-gateway` | Block 3: Auditing — Gateway Traffic | View the gateway audit log |
| `04-auditing-fleet` | Block 4: Auditing — Fleet & Local Activity | Enroll Obot Sentry, scan, hooks, forward local MCP logs |
| `05-filters` | Block 5: Filtering Sensitive Data | Add a source catalog + gateway filters |

## Recommended Order

Run the sections in the order above. Each block's intro assumes the previous block is complete, and each finish points to the next block.
