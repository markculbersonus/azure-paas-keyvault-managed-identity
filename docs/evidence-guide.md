# Screenshot evidence guide

**Author: Mark Culberson**

Recommended filenames for screenshots before uploading to `screenshots/`:

| File | Capture in Azure / terminal | Verification |
|---|---|---|
| `01-sql-database-overview.png` | Azure SQL databases → `sql-app` → Overview | Online status, Basic tier, resource group |
| `02-sql-compute-storage.png` | `sql-app` → Compute + storage | Basic tier, 5 DTUs, storage and redundancy |
| `03-key-vault-overview.png` | Key vaults → `kv-lab03-mark` → Overview | Vault name, region, soft-delete |
| `04-secret-list.png` | `kv-lab03-mark` → Objects → Secrets | `SqlAdminPassword` enabled; **never open/capture secret value** |
| `05-vm-managed-identity.png` | Virtual machines → `vm-web` → Security → Identity | System-assigned status On |
| `06-key-vault-rbac.png` | `kv-lab03-mark` → Access control (IAM) → Role assignments | `vm-web` → Key Vault Secrets User |
| `07-secret-retrieval-http-200.png` | VM terminal after safe API request | HTTP status: 200 and success message |
| `08-db-tier-cleanup.png` | `rg-lab02-mark` → Overview | Retained web-tier resources and removed DB-tier resources |
