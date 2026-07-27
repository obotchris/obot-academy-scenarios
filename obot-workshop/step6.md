# Add a Source Catalog

Everything you've added so far came from Obot's built-in catalog. You can also point Obot at **source catalogs** — Git repositories that define additional MCP servers your organisation wants to make available. Obot reads the repository and lists its servers in the catalog for users to install.

In this step you'll add a source catalog. You won't use its servers just yet — one of them, `synthetic-pii`, is used in the final step of this workshop to demonstrate data filtering.

## Add the Catalog Source

1. In the Obot admin UI, navigate to the MCP catalog configuration (**MCP → Catalogs**, or **Sources**)
2. Click **Add Source** (or **Add Catalog**)
3. Enter the Git repository URL:

   ```
   https://github.com/obotchris/academy-catalog
   ```

4. Save the source

Obot syncs the repository and adds its servers to the catalog. Browse the catalog and confirm you can see the servers defined by `academy-catalog` — including **`synthetic-pii`**, which you'll come back to later.

> Source catalogs are how you curate an approved set of MCP servers for your organisation: keep the definitions in Git, and Obot keeps the catalog in sync.
