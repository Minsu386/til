## Create a Bastion — Updated Lab Notes (2025 Edition)

Use **Windows Server 2022 Datacenter: Azure Edition – x64 Gen2** instead of 2019. This image is fully supported in Azure Generation 2 VMs and offers enhanced features including Hotpatch, SMB over QUIC, and extended support.

### Step 1: Set Up VM

- 1.1
    
    Go to **Virtual Machines** → **+ Create Virtual Machine**, then configure:
    
    ✋
    
- Resource group: `enterprise`
- Region: East US
- VM name: `enterprise-d`
- Availability zone: 1
- Image: **Windows Server 2022 Datacenter: Azure Edition – x64 Gen2**
- Size: Standard_D2s_v3
- Username: `azureuser`, Password: `Testing123456`
- Click Review + Create → Create
- 1.2
    
    Once deployed, go to **Overview** → **Connect** > **RDP**, use credentials to test connection, then close.
    
    ✋
    

### Step 2: Automatic Bastion Deployment

- 2.1
    
    In the VM's menu, select **Bastion**:
    
    ✋
    
- If not deployed, click **Deploy Bastion**.
- Azure will auto-create relevant infrastructure (subnet, Bastion host with Standard SKU, IP).

### Step 3: Connect Using Bastion

- 3.1
    
    After deployment (~10 min):
    
    ✋
    
- Enter `azureuser` / `Testing123456` in the connection pane and click **Connect**.
- Session opens through HTML5 (port 443) in the portal.
- Optionally remove VM's public IP if no longer needed.

### Step 4: Clean-Up

- 4.1
    
    Delete the **enterprise** resource group to halt any incurred charges.
    
    ✋
    

### Reference

[Quickstart: Deploy Azure Bastion automatically](https://learn.microsoft.com/en-us/azure/bastion/quickstart-host-portal)