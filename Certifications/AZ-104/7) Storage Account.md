**Storage Accounts** - A service for various storage types, each with different features and their own pricing models.

**General-Purpose v1 (Legacy)** 
- **Type** - Blob, File, Queue, Table
- **Performance Tiers** - Standard
- **Replication** - LRS, GRS, RA-GRS
- **Deployment Models** - ARM, Classic

**General-Purpose v2** 
- **Type** - Blob, File, Queue, Table, Disk, Data Lake Gen2
- **Performance Tiers** - Standard, Premium
- **Access Tiers** - hot, Cool, Archive (standard only)
- **Replication** - LRS, GRS, RA-GRS, ZRS, GZRS, RA-GZRS

**Blob Storage (Legacy)** - 
- **Type** - Blob (Block, Append) 
- **Performance Tiers** - Standard
- **Access Tiers** - Hot, Cool, Archive
- **Replication** - LRS, GRS, RA-GRS

**Block Blob Storage** 
- **Types** - Blob (Block, Append)
- **Performance Tiers** - Premium
- **Replication** - LRS, GRS, RA-GRS

**File Storage**
- **Type** - Files
- **Performance Tiers** -  Premium
- **Replication** - LRS, ZRS

**Azure Storage Services**
- **Azure Blob** - A scalable Object Store for text and binary data, Supports big data analytics via Data Lake Storage Gen2
- **Azure Files** - Managed file shares for cloud or on-premises deployments
- **Azure Queues** - A NoSQL store for schemaless storage of structured data
- **Azure Tables** - A messaging store for reliable messaging between application components
- **Azure Disks** - Block-level storage volumes for Azure VMs.

**Performance Tiers for Blob Storage** 
- **Standard Performance** - Stored on HDDs
- **Premium Performance** - Stored on SDD
- **Access Tiers** - Hot, Cool, Archive (standard only)

**Types of Blobs**
- **Block Blobs** - Store text and binary data, managed individually
- **Append Blobs** - Optimized for append operations, ideal for logging data from virtual machine
- **Page Blobs** - Store random access files up to 8 TB, serve as disks for Azure Virtual machine

**Blob Lifecycle Management**
- **Role-Based Policies** - Transition data to different tiers (e.g, after 30days move to cool storage)
- **Operations** 
    - **From Cooler Tier** - Billed as a write operation
    - **From Hotter Tier** - Billed as a read operation
- **Cool and Archive Early Deletion** - Early deletion charges may apply


**Replication Types** 
- **Primary Region Redundancy** 
    - **Locally Redundant Storage (LRS)** - Copies data synchronously in the primary region. **Cheapest Option**
    - **Zone-Redundant Storage (ZRS)** - Copies data synchronously across 3 AZs in the primary region
- **Secondary Region Redundancy**
    - **Geo-Redundant Storage (GRS)** - Copies data synchronously in the primary region, asynchronously to another region
    - **Geo-Zone-Redundant Storage (GZRS)** - Copies data synchronously across 3 AZs in the primary region and asynchronously to another region.
- **Read Access Redundancy** 
    - **Read-Access Geo-Redundant Storage (RA-GRS)**
    - **Read-Access Geo-Zone-Redundant Storage RA-GZRS)**


**Azure Files**
- **Managed File Shares** - Centralized server for storage with multiple connections.
- **Mounting** - The file share's filesystem will be accessible within your directory tree
- **Backup** - Use shared snapshots for backup, retain for up to 10 years.
- **Store Tiers**: 
    - **Premium** - SSD with single-digit millisecond latency
    - **Transaction Optimized** - HDD with heavy workload optimization
    - **Hot** - Optimized for general-purpose file sharing.
    - **Cool** - Cost-efficient storage on HDD for archive scenarios 
- **Encryption**:
    - **At Rest**: Using Azure Storage Service Encryption (SSE)
    - **In Transit**: Using SMB 3.0+ with encryption or HTTPS
- **Azure File Sync**: Cache Azure File shares on an on-premises Windows Server or Cloud VM