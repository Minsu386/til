## **Lab Notes: Setup an Azure Firewall to Protect a Virtual Network**

### Step 1: Launch a Virtual Machine

-   1.1
    
    **Navigate to Virtual Machines:**
    
    ✋
    
-   Go to the Azure Portal > **Virtual Machines**.
-   Click on **\+ Add** to create a new virtual machine.
-   1.2
    
    **Set Up the Virtual Machine:**
    
    ✋
    
-   **Resource Group:** Create a new one, e.g., `cardassia`.
-   **Name:** `cardassia-prime`.
-   **Region:** Choose **Canada East** or another preferred region.
-   **Image:** Select **Windows Server 2019 Gen2**.
-   **Size:** Use `Standard_D2_v3` (2 vCPUs, 4 GB RAM).
-   **Administrator Username:** `azureuser`.
-   **Password:** `Testing123456` (with a capital T).
-   Leave all other options as default.
-   1.3
    
    **Review and Create:**
    
    ✋
    
-   Click on **Review + Create** and then **Create** to deploy the VM.

### Step 2: Create an Azure Firewall

-   2.1
    
    **Navigate to Firewalls:**
    
    ✋
    
-   In the Azure Portal, search for **Firewalls** in the top search bar.
-   2.2
    
    **Create a New Firewall:**
    
    ✋
    
-   Click **\+ Add**.
-   Set the following configurations:
    -   **Resource Group:** Select `cardassia`.
    -   **Name:** `space-defense`.
    -   **Tier:** Choose **Standard**.
    -   **Firewall Management:** Stick with **Classic Rules**.
    -   **Virtual Network:** Select `cardassia-vnet` (or use the existing one from the VM).
    -   **Firewall Subnet:** Ensure there is a subnet named **AzureFirewallSubnet**.
    -   If missing:
        -   Go to **Virtual Networks** > `cardassia-vnet` > **Subnets**.
        -   Add a new subnet with the name `AzureFirewallSubnet` and **Address Range:** `10.0.3.0/24`.
-   2.3
    
    **Public IP:**
    
    ✋
    
-   Create a new public IP address named `firewall-ip`.
-   2.4
    
    **Create the Firewall:**
    
    ✋
    
-   Click on **Review + Create** and then **Create**.

### Step 3: Set Up a Route Table for the Firewall

-   3.1
    
    **Navigate to Route Tables:**
    
    ✋
    
-   Search for **Route Tables** in the Azure Portal.
-   3.2
    
    **Create a Route Table:**
    
    ✋
    
-   **Resource Group:** `cardassia`.
-   **Name:** `firewall-route`.
-   Leave **Propagate Gateway Routes** enabled.
-   3.3
    
    **Associate the Route Table with the Subnet:**
    
    ✋
    
-   Go to the **Route Table** > **Subnets**.
-   Click **\+ Associate**.
-   Select the **Virtual Network** (`cardassia-vnet`) and the **default subnet**.
-   3.4
    
    **Add a Route for the Firewall:**
    
    ✋
    
-   In the **Route Table**, go to **Routes** > **\+ Add**.
-   Configure the route:
    -   **Route Name:** `firewall-route`.
    -   **Address Prefix:** `0.0.0.0/0` (to direct all outbound traffic).
    -   **Next Hop Type:** `Virtual Appliance`.
    -   **Next Hop Address:** Enter the **private IP** of the Azure Firewall (found in the Firewall resource under **Private IP Address**).

### Step 4: Create Firewall Rules

-   4.1
    
    **Application Rule:**
    
    ✋
    
-   Navigate to the Firewall resource (`space-defense`) > **Rules** > **Application Rules**.
-   Click **\+ Add a Rule Collection**:
    -   **Name:** `google-collection-rule`.
    -   **Priority:** `200`.
    -   **Source Type:** `IP Address`.
    -   **Source IP Address:** `10.0.2.0/24`.
    -   **Target FQDNs:** `www.google.com` (HTTP/HTTPS).
-   4.2
    
    **Network Rule:**
    
    ✋
    
-   4.3
    
    **NAT Rule:**
    
    ✋
    
-   Add a **NAT Rule Collection**:
    -   **Name:** `rdp-nat-rule`.
    -   **Priority:** `200`.
    -   **Protocol:** `TCP`.
    -   **Source IP Address:** `*` (anywhere).
    -   **Destination IP:** **Firewall Public IP**.
    -   **Destination Port:** `3389` (RDP).
    -   **Translated Address:** **Private IP** of the virtual machine (e.g., `10.0.2.4`).
    -   **Translated Port:** `3389`.

### Step 5: Update DNS Settings

-   5.1
    
    **Update DNS on the Virtual Machine:**
    
    ✋
    
-   Navigate to the VM > **Networking** > **Network Interface** > **DNS Servers**.
-   Set to **Custom**:
    -   **DNS Server 1:** `209.244.0.3`.
    -   **DNS Server 2:** `209.244.0.4`.
-   5.2
    
    **Save Changes.**
    
    ✋
    

### Step 6: Test Connectivity

-   6.1
    
    **Remote Desktop Connection:**
    
    ✋
    
-   Open **Remote Desktop Connection**.
-   Enter the **Public IP of the Firewall**.
-   Use the VM credentials:
    -   **Username:** `azureuser`.
    -   **Password:** `Testing123456`.
-   6.2
    
    **Verify Application Rule:**
    
    ✋
    
-   Open a browser on the virtual machine.
-   Try accessing:
    -   **[www.google.com](http://www.google.com/)** (allowed).
    -   **microsoft.com** (blocked).

### Step 7: Clean Up Resources

-   7.1
    
    To avoid costs, delete all resources:
    
    ✋
    
-   Go to the **Resource Group** (`cardassia`).
-   Click on **Delete Resource Group**.

* * *

### **Key Notes:**

-   **Routing:** Routes are explicitly overridden using a route table to direct traffic through the Azure Firewall.
-   **Firewall Rules:** Rules can be application-based, network-based, or NAT-based.
-   **Testing:** DNS servers and RDP connections are key steps to test firewall rules.