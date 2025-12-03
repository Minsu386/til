

Azure Backup Service is a backup layer that spans many Azure Services.
- On-Prem, Azure VMs, Azure Files, SQL Server (via Azure VM), SAP HANNA databases (via Azure VM), Azure Database for PostgreSQL
- Azure Backup is directly integrated with Azure Services ( you won't find it by serarching based on the service name)
- Offload on-prem backups
- backup your VMs
- Scales Easily
- Get unlimited data transfer (no limit and no charge)
- Keep data secure (build-in security at-rest and in-transit)
- Centralized monitoring and management
- App Consistent Backups (Restore apps back to an exact state)
- Automatic Storage Management
- Multiple Storage Options

Azure Recovery Service (ARS) Vault is  a storage entity in Azure that houses data and recovery points created over time
- Enhanced capabilities to help secure backup data
- Central Monitoring for your hybrid IT environment
- Azure role-based access control (Azure RBAC) 
- Soft Delete
- Cross Region Restore

Microsoft Azure Recovery Services (MARS) agent backups files, folders, and systems state from windows on-prem machines and Azure VMs
- Backups are stored in a Recovery Services vault in Azure
- MARS agent is also known  as the Azure Backup Agent
- The MARS agent does not support Linux OS
- Azure Site Recovery (ASR) is a hybrid backup solution for site-to-site recovery