## Create a Recovery Services vault and Enable VM Backup

### Step 1: Create a Virtual Machine

-   1.1
    
    In the Azure portal, search for **Virtual Machines** in the search bar.
    
    ✋
    
-   1.2
    
    Click **\+ Create → Azure virtual machine**.
    
    ✋
    
-   1.3
    
    Fill in the following details:
    
    ✋
    
-   **Resource Group**: Create new → `picard`
-   **Virtual machine name**: `picard` (or another available name)
-   **Region**: `Central US`
-   **Image**: Windows Server 2019 Datacenter - Gen2
-   **Size**: Standard\_B2s (2 vCPUs, 4 GiB memory)
-   **Administrator account**:
    -   Username: `azureuser`
    -   Password: `Testing123456`
-   Leave defaults for networking, disks, etc.
-   1.4
    
    Click **Review + Create**, then **Create**.
    
    ✋
    

### Step 2: Create a Recovery Services vault

**Important:** The vault must be in the **same region** as the VM.

-   2.1
    
    In the search bar, type **Backup center** and open it.
    
    ✋
    
-   2.2
    
    In **Backup center**, select **Vaults → + Vault**.
    
    ✋
    
-   2.3
    
    Choose **Recovery Services vault**, then click **Continue**.
    
    ✋
    
-   Resource group: `picard`
-   Vault name: `picardbackup`
-   Region: `Central US` (must match the VM region)
-   2.4
    
    Click **Review + Create**, then **Create**.
    
    ✋
    

### Step 3: Enable Backup for the VM

-   3.1
    
    In the Recovery Services vault (`picardbackup`), select **\+ Backup**.
    
    ✋
    
-   3.2
    
    Fill in the options:
    
    ✋
    
-   **Where is your workload running?** → Azure
-   **What do you want to back up?** → Virtual machine
-   3.3
    
    Create a new **Backup policy**:
    
    ✋
    
-   Timezone: your local timezone
-   Keep defaults for backup frequency and retention
-   Add the virtual machine: `picard`
-   Click **Enable Backup**

### Step 4: Verify the Backup

-   4.1
    
    In your `picardbackup` vault, go to **Backup items**.
    
    ✋
    
-   4.2
    
    To confirm: open **Backup policies**, click **\+ Add** → select **Azure Virtual Machine**,
    
    ✋
    
-   Policy name: `MySpecialPolicy`
-   Click **Create**
-   4.3
    
    Go to the VM `picard` → **Backup** blade → **Backup policy**.
    
    ✋
    
-   4.4
    
    Change the policy to **MySpecialPolicy** if desired.
    
    ✋
    

### Step 5: Cleanup

-   5.1
    
    When finished, delete the **resource group `picard`** to remove the VM, vault, and related resources.
    
    ✋
    

### Key Update Notes:

-   Ensure the **Recovery Services vault and VM are in the same region**.
-   Use **Recovery Services vault** (not Backup vault) when backing up Azure VMs.
-   VM will not appear as backup-eligible unless these requirements are met.