# Azure Backup & Disaster Recovery Dashboard

Azure Workbook for monitoring backup coverage and disaster recovery readiness across VMs, PostgreSQL databases, and Recovery Vaults.

## What's Included

### Coverage Tables
- **VM Backup Coverage** - Track protected vs unprotected VMs per subscription with coverage percentages
- **PostgreSQL Backup Coverage** - Monitor vault-based backup adoption for PostgreSQL Flexible Servers

### Detailed Resource Views
- **VM Backup Details** - Per-VM protection status, vault links, backup policies, and last restore points
- **PostgreSQL Backup Details** - Per-server vault backup status and protection state

### DR Readiness
- **Recovery Vault Inventory** - Vault security posture including soft delete, cross-region restore, and protected items

## Queries

1. **VM Backup Coverage** - Aggregates VM backup status across subscriptions (Good ≥80%, Fair ≥50%)
2. **PostgreSQL Backup Coverage** - Tracks vault-based backup adoption (built-in backup always enabled)
3. **VM Backup Details** - Per-VM view with protection status (✅ Protected / ⚠️ Unprotected), vault ID, policy, and last restore point
4. **PostgreSQL Backup Details** - Per-server vault backup configuration and protection state
5. **Recovery Vault Inventory** - Vault security assessment (soft delete, cross-region restore, protected items)

## Deployment

1. Open [Azure Portal](https://portal.azure.com) → **Monitor** → **Workbooks** → **+ New**
2. Click **Advanced Editor** (</> icon) in the toolbar
3. Replace the JSON content with `workbook.json` from this folder
4. Click **Apply** → **Done Editing** → **Save**
5. Provide name, subscription, resource group, and location

## Important Notes

**Azure SQL Database & SQL MI** have automatic platform backups. However, Azure Resource Graph (ARG) cannot retrieve PITR retention, differential backup frequency, LTR policies, or immutability settings. Use Azure Portal, CLI, or PowerShell for complete SQL backup policy details.
