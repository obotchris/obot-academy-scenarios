# Add a Source Catalog & Baseline the PII Data

Least privilege (step 1) removed `get_customer` for the support agent. But suppose a *different* agent genuinely needs it. You can let the call through and **strip sensitive fields at the gateway** before they reach the client. First, stand up a clean PII data source and get a baseline.

## Step 1: Add a Source Catalog

Point Obot at a Git repository that defines additional MCP servers your organisation approves.

1. In the Obot admin UI, navigate to **MCP Management → MCP Catalog**, then the **Catalog Sources** tab
2. Click **Add Source** (or **Add Catalog**)
3. Paste the repository URL below and **Save**:

```
https://github.com/obotchris/academy-catalog
```{{copy}}

Obot syncs the repository and lists its servers in the catalog — including **`customer-demo-data`**, which returns fake records (names, emails, and US driver's licence numbers): safe test data for exercising filters.

> Curating an approved catalog is itself a control — it's the "approved registry" angle from Lab A's poisoned-description bonus. You decide which servers and tools are even installable.

## Step 2: Add customer-demo-data and Expose It Through a vMCP

1. In the catalog, find **`customer-demo-data`** and add it as an MCP server
2. Go to **All Resources → vMCPs → Create vMCP**, drag `customer-demo-data` onto the **+CREATE NEW VMCP** target, name it `customer-demo-data`, and **Create** (choose **As-Is**)
3. Open the vMCP, click **Connect**, copy the **Connection URL**, and add it to Claude Code:

```bash
claude mcp add --transport http "customer-demo-data" "<connection URL>"
```{{copy}}

## Step 3: Baseline — No Filter Yet

In a Claude Code session:

> List the data from the customer-demo-data server.

Records come back **in full** — names, emails, and driver's licence numbers all visible. This is the baseline you'll now filter.
