## Lab Notes: Azure Setup Test Server for Network Watcher

### Objective

Set up a test web server on an Azure Virtual Machine (VM) running Apache2 and use Network Watcher to verify and troubleshoot network connections.

### Prerequisites

-   Azure Portal access
-   Basic familiarity with SSH and Linux commands

### Step 1: Launch a New Virtual Machine

-   1.1
    
    Go to **Azure Portal** > **Virtual Machines**.
    
    ✋
    
-   1.2
    
    Click **Create** to launch a new VM.
    
    ✋
    
-   1.3
    
    Configure the virtual machine:
    
    ✋
    
-   **Name**: `risa`
-   **Region**: Any preferred region (make note of it).
-   **Image**: `Ubuntu Server LTS` (Generation 2).
-   **Size**: `Standard B1ls` (cheapest available).
-   1.4
    
    Configure authentication:
    
    ✋
    
-   **Username**: `azureuser`
-   **Password**: `Testing123456` (capital 'T').
-   1.5
    
    Under **Inbound Port Rules**:
    
    ✋
    
-   Select **Allow HTTP (Port 80)**.
-   1.6
    
    Click **Review + Create**.
    
    ✋
    
-   1.7
    
    Once the validation passes, click **Create**.
    
    ✋
    

### Step 2: Access the Virtual Machine and Install Apache2

-   2.1
    
    Wait for the deployment to complete.
    
    ✋
    
-   2.2
    
    Go to **Resources** > **Virtual Machine** and copy the **Public IP Address**.
    
    ✋
    
-   2.3
    
    Open **Azure Cloud Shell** or a local terminal.
    
    ✋
    
-   2.4
    
    SSH into the VM:
    
    ✋
    

    ssh azureuser@<Public-IP-Address>
    

-   When prompted, type `yes` to accept the connection.
-   Enter the password: `Testing123456`.
-   2.5
    
    Install Apache2:
    
    ✋
    

    sudo apt update
    sudo apt install apache2 -y
    

-   2.6
    
    Verify Apache2 installation:
    
    ✋
    
-   Use the following command to check the default Apache page:

    curl localhost
    

-   If HTML content appears, Apache2 is running locally.
-   2.7
    
    Test in the browser:
    
    ✋
    
-   Copy the **Public IP Address** of the VM.
-   Paste it into a browser: `http://<Public-IP-Address>`.
-   Verify the default Apache2 page loads.

### Step 3: Use Network Watcher for Troubleshooting

-   3.1
    
    Go to **Network Watcher**:
    
    ✋
    
-   In Azure Portal, search for "Network Watcher" in the top search bar.
-   3.2
    
    Verify Network Watcher Provisioning:
    
    ✋
    
-   Under **Regions**, ensure a Network Watcher instance is deployed for your VM's region.
-   If not, enable Network Watcher for that region.

#### Connection Troubleshoot Tool

1.  In Network Watcher, select **Connection Troubleshoot**.
2.  Input the following:
    -   **Source IP**: Your machine's IP (or leave it as `My IP`).
    -   **Destination IP**: The **Public IP Address** of the VM.
    -   **Protocol**: `HTTP`.
3.  Click **Test Connection**.
    -   Wait for the tool to confirm the connection status.

#### Verify Apache2 is Running

1.  Back on the VM terminal, check if Apache2 is running:

    ps aux | grep apache2
    

-   Confirm Apache processes are active.

#### Other Useful Network Tools

-   **IP Flow Verify**: Checks if traffic is allowed through the Network Security Group (NSG).
-   **NSG Diagnostics**: Debugs NSG rules.
-   **Traffic Analytics**: Analyzes network traffic flow.
-   **Topology**: Visualizes the VM network setup.

### Step 4: Final Verification

-   4.1
    
    Refresh the **Public IP Address** in your browser to confirm the Apache page still loads.
    
    ✋
    
-   4.2
    
    Use **Connection Troubleshoot** and **IP Flow Verify** for any network issues.
    
    ✋