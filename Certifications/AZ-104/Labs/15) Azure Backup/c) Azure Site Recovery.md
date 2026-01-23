## Set Up Disaster Recovery for Azure VMs with Site Recovery Lab Notes (Updated Sep 2025)

### What’s New / Key Changes

Before walking through the lab, note these important updates:

-   **Premium SSD v2 (Pv2) disk support** is now **in public preview** for Azure Site Recovery.
-   Source VMs with Premium SSD v2 disks can be replicated if region, VM size, and availability options meet the preview requirements.
-   NVMe disk controllers are _still_ **not supported** for ASR. Some newer VM families (e.g. Eas\_v6, Das\_v6 variants) use NVMe controllers and these are explicitly excluded.
-   For VMs with Pv2 disks / Ultra Disks etc., ASR requires using the **High Churn option** for cache / storage configuration.

### Step 1: Verify Prerequisites

-   1.1
    
    **Azure subscription** + a supported VM (Windows or Linux).
    
    ✋
    
-   1.2
    
    Permissions: Owner/Admin (for vault), Site Recovery Contributor, VM Contributor.
    
    ✋
    
-   1.3
    
    Target region has enough VM quota, compatible VM SKUs, and **availability zones** if needed.
    
    ✋
    
-   1.4
    
    Ensure outbound connectivity (to Azure storage, Entra ID, Site Recovery, Service Bus etc.).
    
    ✋
    
-   1.5
    
    VM OS and data disks must have up-to-date certificates.
    
    ✋
    
-   **New check**: Determine whether your VM disks are Premium SSD v2 or using NVMe controllers.
-   You can look in the VM’s disk settings / SKU documentation.
-   If using Premium SSD v2 AND your region supports ASR preview for Pv2, you may proceed with those disks. If the VM uses NVMe controllers → replication will fail.
-   Use the **Support Matrix** (Azure VM Disaster Recovery between Azure regions) to check if your VM SKU + disk type are supported.

### Step 2: Create a Recovery Services Vault

-   Same as original: Subscription, Resource group, Vault name, Vault region.
-   **Ensure vault region is one that supports the features you plan to test** (e.g. Pv2, High Churn) if you’ll use those.

### Step 3: Enable Site Recovery

-   Go to the vault → **Site Recovery** → **Enable Site Recovery**.

### Step 4: Enable Replication for VMs

-   4.1
    
    In vault, select **Enable replication** under Azure Virtual Machines.
    
    ✋
    
-   4.2
    
    **Configure Source Settings**:
    
    ✋
    
-   Region, subscription, RG, etc.
-   **Availability options**: If using Pv2 disks, VM often must be **zonal**; Pv2 disks typically must be attached to VMs in a particular zone.
-   If VM uses an availability set (non-zonal), check whether it’s compatible. If not, may need to convert or use another VM.
-   4.3
    
    Select VMs to protect.
    
    ✋
    
-   4.4
    
    **Replication policy settings**:
    
    ✋
    
-   For Pv2 / Ultra Disks: you must choose **High Churn** storage (cache) option.
-   Default recovery point retention, snapshot frequency – as usual.
-   4.5
    
    Manage options:
    
    ✋
    
-   If you require failover of several VMs together, use **Recovery plans** or replication groups.
-   Ensure extension service (Mobility service) is installed.
-   4.6
    
    Review + enable replication.
    
    ✋
    

### Step 5: Monitor Replication

-   5.1
    
    Check “Replicated items” in vault.
    
    ✋
    
-   5.2
    
    Confirm **Site Recovery Mobility service** is installed.
    
    ✋
    
-   5.3
    
    Ensure status becomes **Protected**.
    
    ✋
    
-   **New check**: If using Pv2 disks, after enabling replication, monitor whether the initial synchronization (hydration) completes OK. Also verify that the cache / storage settings are correct (High Churn) and that you don’t get errors related to disk controller (NVMe) or unsupported VM SKU.

### Step 6: Clean Up (Optional)

-   Same as before: Stop replication, delete vault or resources if unneeded.

### Step 7: Additional Debugging Tips & Errors

-   **Error 1400119**: Means VM uses **NVMe disk controller** or unsupported VM family. If encountered, either move to a supported VM SKU, switch disk type, or avoid NVMe.
-   If you get an error about “cannot proceed without zone settings” or “availability zone required”, check that your VM is zonal and disk type matches region’s Pv2 availability.
-   If using Pv2, ensure your region has matching support for Pv2 + ASR public preview. If region doesn’t support that yet, you'd have to use Premium SSD v1 or another supported disk type.

### Example Modified Lab Flow (incorporating Pv2)

Here’s an example path if you’re using Pv2 disks and your region supports ASR preview for them:

1.  Pick a region that supports **Pv2 with ASR preview**. Use Azure CLI / portal to validate.
2.  Create or identify a **zonal VM**: VM must be in a zone AND use Premium SSD v2 for data disks (OS disk may or may not be supported depending on preview limitations).
3.  Ensure that during disk creation or attachment, you specify the correct SKU (PremiumV2\_LRS or PremiumV2 with zone) and that availability zone is set.
4.  Create Recovery Services vault in target region that is supported.
5.  Enable ASR, selecting the VM. Under replication settings, choose High Churn, ensure cache is premium/high-performance.
6.  Proceed, monitor for hydration, confirm status.

### Reference

-   [Set up disaster recovery for Azure VMs](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-tutorial-enable-replication)
-   [Azure to Azure disaster recovery architecture](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-architecture)