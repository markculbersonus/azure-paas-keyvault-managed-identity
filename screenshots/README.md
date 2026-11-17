# Azure PaaS — screenshot evidence index

This index identifies the **actual visible content** of each uploaded image. Historical filenames are preserved temporarily for link compatibility; filenames are **not** evidence of the resource depicted.

| Existing file | Actual screenshot content | Evidence interpretation |
|---|---|---|
| `01-sql-database-overview.png` | Former database-tier VM | Historical IaaS VM, **not** Azure SQL Database |
| `02-sql-logical-server.png` | Former DB VM managed disk | Historical managed disk, **not** SQL logical server |
| `03-key-vault-overview.png` | Azure Key Vault overview | Key Vault resource |
| `04-key-vault-secret-list.png` | Key Vault secret list | Secret inventory; never disclose values |
| `05-vm-managed-identity.png` | Azure SQL compute/storage configuration | Database configuration, **not** VM identity |
| `06-key-vault-rbac.png` | Key Vault RBAC screen | Role configuration/review; review alone is not proof of completion |
| `07-secret-retrieval-http-200.png` | Key Vault REST API status | HTTP 200 verification, not a database connection |
| `08-db-tier-cleanup.png` | Azure resource group inventory | Resource inventory; not standalone before/after proof |

## Additional evidence to upload

- `azure-sql-logical-server-overview.png`: Original Azure SQL logical server `sql-server-markk` screenshot with `sql-app` online.
- `vm-web-system-assigned-managed-identity.png`: Original `vm-web` Identity screenshot showing system-assigned identity **On**.

Before publication, review images at full resolution and obscure account emails, subscription/tenant IDs, principal/object IDs, tokens, passwords, and secret values. **Keep Azure service, resource, and object names readable** (such as `sql-app`, `sql-server-markk`, `vm-web`, `kv-lab03-mark`). Do not use blanket blur over technical evidence.
