# Azure PaaS project — screenshot evidence

These are **real screenshots** sourced from the user's previously uploaded Azure captures, with **soft Gaussian blur** applied to browser/account headers where relevant (no black bars).

**Important:** Blur does not guarantee removal of sensitive information. Before publishing, visually inspect each image at full resolution for subscription IDs, tenant/object IDs, emails, public IP addresses, access tokens, credentials and secret values. Some screens may represent configuration/review rather than completed verification.

| File | Evidence |
|---|---|
| `01-sql-database-overview.png` | Azure SQL Database overview |
| `02-sql-logical-server.png` | SQL logical server overview |
| `03-key-vault-overview.png` | Key Vault overview |
| `04-key-vault-secret-list.png` | Key Vault secrets list |
| `05-vm-managed-identity.png` | Web VM managed identity settings |
| `06-key-vault-rbac.png` | Key Vault role assignments |
| `07-secret-retrieval-http-200.png` | Successful secret retrieval HTTP 200 |
| `08-db-tier-cleanup.png` | Resource group inventory after cleanup |

## GitHub upload

1. Open your GitHub repository and enter the `screenshots/` directory.
2. Choose **Add file → Upload files**.
3. Upload the eight PNG files from this directory.
4. Commit with `Add Azure PaaS screenshot evidence`.
5. Edit your root `README.md` and add image references from `README-INSERT.md`.
6. Preview, verify all images render, and commit.

Resource names in Azure may retain `lab02` or `lab03` because those are real resource identifiers; the portfolio project title need not use lab numbering.
