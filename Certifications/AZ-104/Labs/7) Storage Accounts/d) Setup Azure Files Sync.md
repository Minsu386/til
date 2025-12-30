## Setup Azure File Sync Follow Along

### Step 1: Create Virtual machine, Create Storage Account, Create File Share, and Create Storage Sync Service

### Create a Virtual Machine:

- 1.1
    
    Search for "Virtual Machine" in the Azure portal and click "+ Add" to create a **Virtual Machine**
    
- Enter the following information:
    - **Resource Group**: Create a new resource group named `kivas-rg`.
    - **Virtual Machine Name**: `kivas-vm` (or a name of your choice).
    - **Region**: East US.
    - **Image**: Windows Server 2019 Datacenter Gen 2.
    - **Size**: Standard_B1ms - 1 vCPU, 2 GiB memory (ensure it meets the minimum requirements for a server with a desktop interface).
    - **Username**: `azureuser`
    - **Password**: `Testing123456`
    - **Inbound Ports**: Select HTTP (80), HTTPS (443), and RDP (3389).
- Go to the Disk section and create a new disk (if needed):
    - **Disk Name**: `kivas-disk` (choose a name).
    - **Disk Size**: 1024 GiB.
    - **Enable Shared Disk**: No (default).
- Click **Review + Create** and then **Create**.

### Create a Storage Account:

- 1.2
    
    Go to "Storage Accounts" and click "+ Add" to create a new storage account.
    
- Enter the following information:
    - **Resource Group**: `kivas-rg`
    - **Region**: (US) US East
    - **Storage Account Name**: `kivas-sa`
    - **Performance**: Standard
- Click **Review + Create** and then **Create**.

### Create a File Share:

- 1.3
    
    In the `kivas-sa` storage account, navigate to "**File shares**".
    
- Click "+ File Share" to create a new file share.
- Enter the following information:
    - **Name**: `kivas-fs`.
    - **Tier**: Transaction Optimized.
    - **Quota**: 5 (optional).
- Click **Create**.

### Create Storage Sync Service:

- 1.4
    
    Search for "Storage Sync Services" and click on it.
    
- Click "+ Add" to create a new sync service.
- Enter the following information:
    - **Resource Group**: `kivas-rg`.
    - **Storage Sync Service Name**: `kivas-sss`.
    - **Region**: East US.
- Click **Review + Create** and then **Create**.

### Connect to the Virtual Machine:

- 1.5
    
    Go back to the `kivas-vm` virtual machine.
    
- Click **Connect**, select **RDP**, and click "Download RDP File".
- Enter the username `azureuser` and the password `Testing123456` created earlier.
- Click **OK** and **Connect**.

### Step 2: Install-Module AzureRM, Create Sync Group, Install Azure File Sync

- 2.1
    
    Run Windows PowerShell as administrator
    
- 2.2
    
    Install-Module -Name AzureRM - AllowClobber [There will be a wait time]
    

**Note**: AllowClobber: Overrides warning messages about installation conflicts about existing commands on a computer. Overwrites existing commands that have the same name as commands being installed by a module. AllowClobber and Force can be used together in an Install-Module command.

[Parameters](https://docs.microsoft.com/en-us/powershell/module/powershellget/install-module?view=powershell-7.1#parameters)

- 2.3
    
    **Press Y for all options**, and let it install.
    
- 2.4
    
    Go to **Storage Sync Services** - `kivas-sss`, Create a +**Sync Group**, Sync Group name: `kivas-sg`, Select storage account: `kivas-sa`, Azure File Share: `kivas-fs`, Click Create
    
- 2.5
    
    Click on the `kivas-sg`, Click on **Add cloud endpoint**, Select storage account: `kivas-sa`, Azure File Share: `kivas-fs`, Click Create.
    
- 2.6
    
    In your virtual machine, go to Server Manager and turn off IE Enhanced Security Configuration, Go to [https://www.microsoft.com/en-us/download/details.aspx?id=57159](https://www.microsoft.com/en-us/download/details.aspx?id=57159) to download **Azure File Sync Agent** and download StorageSyncAgent_WS2019.msi which is the server launched.
    
- 2.7
    
    Run **Storage Sync Agent Setup**, Agree to terms, default settings are fine for all options, proceed to install and Finish.
    

### Step 3: Azure File Sync

- 3.1
    
    Select Azure Environment - Azure Cloud, Sign into Microsoft account. Choose Azure subscription, resource group: `kivas-rg`, and storage sync service: `kivas-sss` and hit register. Registration Successful!
    
- 3.2
    
    Go to File Explorer, Attach a new data disk in Azure, format it, and assign it to `D:\` or another available drive letter. Then create a new folder named `kivas-share`, inside the folder, create a text file named hello.txt. Right-click on `kivas-share` folder and turn on Share.
    

**Note:** Cloud Tiering cannot be enabled on `C:\`. Ensure the `kivas-share` folder is located on another drive, such as `D:\`.

- 3.3
    
    Go back to Azure portal, navigate to **Storage Sync Services**, click on `kivas-sss`, click on **Sync groups**,
    
- 3.4
    
    Click on `kivas-sg`, click on Add **server endpoint**, Registered Server: `kivas-vm`, Path: `D:\kivas-share`, **turn on "Cloud Tiering"**, Click **Create**.
    
- 3.5
    
    Azure File Sync should be active! Go to Storage Accounts: `kivas-sa`, File Shares: `kivas-fs`. You should be able to see hello.txt from your Virtual machine. These files are in sync so if you create a file from the virtual machine, you should see them on the storage account file share - `kivas-fs`
    
- 3.6
    
    Delete cloud endpoint, delete server endpoint, delete all resources in `kivas-sg` and the resource group.
    
- You may need to go to `kivas-sss` Storage Sync Services, click on Registered Servers, and unregister `kivas-vm` to delete cloud endpoint.

### Reference

- [Deploy Azure File Sync](https://docs.microsoft.com/en-us/azure/storage/file-sync/file-sync-deployment-guide?tabs=azure-portal%2Cproactive-portal)
- [Azure File Sync Agent](https://www.microsoft.com/en-us/download/details.aspx?id=57159)