# Security design and lessons learned

**Author: Mark Culberson**

## Why PaaS?

Replacing a self-managed database-tier VM with Azure SQL Database reduces the infrastructure and operating system maintenance required for the database platform. Azure still requires deliberate configuration of authentication, network access, data security, monitoring, and cost controls.

## Why Key Vault?

Storing `SqlAdminPassword` in Azure Key Vault separates a sensitive credential from application source code and version control. The secret remains protected by Azure access controls.

## Why managed identity?

The Ubuntu web VM uses a system-assigned managed identity to obtain a Microsoft Entra token for Azure Key Vault. This removes the need to store a separate Key Vault client secret on the VM.

## Why RBAC?

The vault-scoped `Key Vault Secrets User` role authorizes the VM identity to read secret values. This illustrates the separation of **authentication** (identity/token) from **authorization** (RBAC permission).

## Validation outcome

The authenticated secret request returned HTTP 200. The response body was discarded, keeping the secret value out of the terminal evidence.

## Improvements for a production iteration

- Restrict SQL and Key Vault networking with private endpoints where feasible.
- Prefer Microsoft Entra-based SQL authentication and minimize SQL administrator credential use.
- Enable diagnostic logging, monitoring alerts, and secret rotation procedures.
- Evaluate Key Vault purge protection and operational recovery requirements.
- Scope permissions to only the identities and resources that require them.
