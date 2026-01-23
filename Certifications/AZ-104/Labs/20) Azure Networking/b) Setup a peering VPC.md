## Azure Virtual Network Peering Lab Notes

### Objective

Set up Virtual Network (VNet) Peering between two VNets in the same region (**Local Peering**) and one VNet in a different region (**Global Peering**). Test connectivity between them using PowerShell commands.

### Prerequisites

-   Azure subscription
-   Familiarity with the Azure Portal
-   Remote Desktop Protocol (RDP) client installed on your local machine (Windows or Mac).

### Step 1: Set Up Resource Group and Virtual Machines

-   1.1
    
    **Create a Resource Group**
    
    ✋
    
-   Navigate to the Azure Portal.
-   Go to **Resource Groups**.
-   Click **Create**.
-   Name the resource group: `peering-challenge`.
-   Select a region (e.g., **East US**).
-   1.2
    
    **Deploy Three Virtual Machines (VMs)**
    
    ✋
    
-   **VM1**: Region = `East US`, VNet = `East-A-VNet`
-   **VM2**: Region = `East US`, VNet = `East-B-VNet`
-   **VM3**: Region = `West US`, VNet = `West-A-VNet`

#### VM Configuration

-   Go to **Virtual Machines** > **Create VM**.
-   For each VM:
    -   **Resource Group**: `peering-challenge`
    -   **VM Name**: `EastA`, `EastB`, or `WestA` as appropriate.
    -   **Region**: Select **East US** or **West US**.
    -   **Image**: Windows Server 2019 Datacenter Gen 2.
    -   **Size**: `Standard_D2_v3` (2 vCPUs, 4GB RAM).
    -   **Administrator Username**: `azureuser`
    -   **Password**: `Testing123456` (capital **T**).
    -   **Virtual Network**:
    -   `EastA`: `East-A-VNet`, Subnet: `10.1.0.0/24`
    -   `EastB`: `East-B-VNet`, Subnet: `10.2.0.0/24`
    -   `WestA`: `West-A-VNet`, Subnet: `10.0.1.0/24`
-   Review and create each VM.

### Step 2: Create Virtual Network Peering

-   2.1
    
    **Navigate to Virtual Networks** in the Azure Portal.
    
    ✋
    
-   2.2
    
    **Peer East-A-VNet to East-B-VNet (Local Peering):**
    
    ✋
    
-   Select `East-A-VNet`.
-   Go to **Peerings** > **\+ Add**.
-   Name the peering: `EastA-to-EastB`.
-   **Peer with Virtual Network**: Select `East-B-VNet`.
-   Block traffic on both sides.
-   Click **Add**.
-   2.3
    
    **Peer East-A-VNet to West-A-VNet (Global Peering):**
    
    ✋
    
-   Select `East-A-VNet`.
-   Go to **Peerings** > **\+ Add**.
-   Name the peering: `EastA-to-WestA`.
-   **Peer with Virtual Network**: Select `West-A-VNet`.
-   Block traffic on both sides.
-   Click **Add**.

### Step 3: Test Connectivity Between Virtual Machines

-   3.1
    
    **Retrieve the IP Addresses**:
    
    ✋
    
-   Go to each VM > **Networking** > Note the **Private IP**:
    -   `EastA`: `10.1.0.4`
    -   `EastB`: `10.2.0.4`
    -   `WestA`: `10.0.1.4`
-   3.2
    
    **RDP into VM1 (EastA):**
    
    ✋
    
-   Connect to `EastA` using RDP.
-   Open **PowerShell**.
-   3.3
    
    **Test Connectivity to EastB** (Same Region):
    
    ✋
    

    Test-NetConnection -ComputerName 10.2.0.4 -Port 3389 -InformationLevel Detailed
    

-   Expected Result: `TcpTestSucceeded: True`

3.4 \[ \] **Test Connectivity to WestA** (Different Region):

    Test-NetConnection -ComputerName 10.0.1.4 -Port 3389 -InformationLevel Detailed
    

-   Expected Result: `TcpTestSucceeded: True`

### Step 4: Clean Up Resources

-   4.1
    
    Navigate to **Resource Groups** > `peering-challenge`.
    
    ✋
    
-   4.2
    
    Select **Delete Resource Group**.
    
    ✋
    
-   4.3
    
    Confirm deletion.
    
    ✋
    

### Notes

-   `Test-NetConnection` is a PowerShell cmdlet for testing connectivity.
-   Use **RDP Bastion** if you face issues connecting via RDP on a Mac.
-   Ensure the VNet subnets do not overlap.

## #Outcome

Successfully configured: - Local Peering between VNets in the same region. - Global Peering between VNets in different regions. - Verified connectivity using PowerShell.