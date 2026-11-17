# Implementation record

**Project:** Azure Azure PaaS project — PaaS Modernization & Secure Secret Management  
**Author:** Mark Culberson

## 1. Modernize the database tier

Retired the previous network project database-tier VM `vm-db-01`, its network interface, OS disk, and DB-specific NSG. Preserved `vm-web`, its supporting resources, and `vnet-lab02` for the next phase.

## 2. Provision managed database services

Created Azure SQL logical server `sql-server-markk` and Azure SQL Database `sql-app` in `rg-lab03-mark`. The database Overview screenshot showed **Online**, Central US, and **Basic** pricing tier. Compute + storage showed 5 DTUs, 2 GB maximum data size, and locally redundant backup storage.

## 3. Store the database credential securely

Created Standard-tier Key Vault `kv-lab03-mark` in `rg-lab03-mark`. Added the enabled secret `SqlAdminPassword`. The secret value is deliberately excluded from all documentation.

## 4. Enable workload identity

Enabled a system-assigned managed identity on the retained Ubuntu VM `vm-web` in `rg-lab02-mark`.

## 5. Grant access through Azure RBAC

Assigned the `Key Vault Secrets User` role to the VM managed identity at the `kv-lab03-mark` resource scope. The IAM role assignments view showed the managed identity and role.

## 6. Verify secret retrieval

From `vm-web`, an authenticated Key Vault REST API request for `SqlAdminPassword` returned **HTTP 200**. The test discarded the response body and printed only the HTTP status and success message. This confirms authorized secret retrieval without exposing the stored password.

## 7. Observability

Reviewed Azure SQL Database monitoring, including CPU, Data IO, and DTU metrics. Some monitoring views displayed a data retrieval error during exploration; do not interpret this as a confirmed database outage.

## Security and accuracy notes

- Azure SQL Database and Key Vault are managed Azure services, while the Ubuntu VM remains IaaS.
- Managed identity authenticates the VM to Azure Key Vault; Azure RBAC authorizes secret access.
- `SqlAdminPassword` is still a SQL administrator credential. The managed identity does not replace SQL administrator authentication.
- Never publish the secret value, bearer token, SSH key, or subscription identifiers.
