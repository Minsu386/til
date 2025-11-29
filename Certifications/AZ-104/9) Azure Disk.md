
**Azure Managed Disks** are block-level storage volumes that are managed by Azure and used with Azure VMs

Managed disks are designed for 99.999% availability

Azure creates three replicas of your data, allowing for high durability

You can create up to 50,000 VM disks of a type in a subscription per region

Allowing you to create up to 1,000 VMs in a virtual machine scale set using a Marketplace image

Managed disks support **Availability Zones**

**Azure Backup** can be used to create a backup job with time-based backups and backup retention policies

You can use **Azure role-based access control (RBAC)**  to assign specific permissions for a managed disk to one or more users

You can directly import your Virtual Hard drive Disk (VHD) into Azure Disks

You can use **Azure Private Links** to ensure traffic between Azure Disks and VMs stay within the Microsoft network

**Azure Managed Disks** supports 2 type of encryption:
- Server Side Encryption (SSE) is enabled by default for all managed disks, snapshots, and images
    - Temporary disks are not encrypted by server-side encryption unless you enable encryption at host
    - Keys can be managed two ways:
        - Platform-managed keys -- Azure manages your keys
        - Customer-managed keys -- You manage your keys
    - Azure Disk Encryption (ADE) allows you to encrypt the OS and Data disks used by an IaaS Virtual Machine
    - For Windows Encryption is done by **BitLocker**
    - For Linux encryption is done by **DM-Crypt**
- 