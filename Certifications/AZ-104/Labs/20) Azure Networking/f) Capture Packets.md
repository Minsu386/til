## Azure Packet Capture Lab Notes

### Objective:

Use Azure Network Watcher's Packet Capture tool to capture and analyze network packets for a virtual machine.

### Step 1: Access Azure Network Watcher

-   1.1
    
    Log in to your Azure portal.
    
    ✋
    
-   1.2
    
    Navigate to **Network Watcher**.
    
    ✋
    

### Step 2: Create a Packet Capture

-   2.1
    
    In the **Network Watcher** menu, select **Packet Capture**.
    
    ✋
    
-   2.2
    
    Click on **\+ Add** to create a new packet capture session.
    
    ✋
    
-   2.3
    
    Fill out the following details:
    
    ✋
    
-   **Name:** Provide a name for your packet capture session (e.g., `risa-packet`).
-   **Target:** Select the virtual machine (VM) you want to monitor.
-   2.4
    
    Choose or create a storage account:
    
    ✋
    
-   If a storage account is not available, the tool will create one automatically.
-   2.5
    
    Configure the following settings:
    
    ✋
    
-   **Maximum Packets:** Leave as `0` to use the default value.
-   **Protocols:** Choose **TCP** (if only monitoring TCP traffic).
-   2.6
    
    Click **Save** to start the packet capture process.
    
    ✋
    

### Step 3: Monitor the Packet Capture

-   3.1
    
    Refresh the page to check the status of the capture.
    
    ✋
    
-   3.2
    
    Wait for the packet capture to begin.
    
    ✋
    

### Step 4: Generate Traffic to Capture

-   4.1
    
    Open the public IP address of your target virtual machine:
    
    ✋
    
-   Navigate to **Virtual Machines** in Azure.
-   Select your VM and copy the **Public IP Address**.
-   Open the IP address in a browser to generate traffic.
-   4.2
    
    Allow traffic to flow for a short period to collect data.
    
    ✋
    

### Step 5: Stop the Packet Capture

-   5.1
    
    Navigate back to the **Packet Capture** section in **Network Watcher**.
    
    ✋
    
-   5.2
    
    Select the active packet capture session.
    
    ✋
    
-   5.3
    
    Click **Stop** to end the capture prematurely if you do not want to wait for the timeout period.
    
    ✋
    
-   5.4
    
    Once stopped, Azure will create a `.cap` file in the specified storage account.
    
    ✋
    

### Step 6: Locate and Download the Capture File

-   6.1
    
    Go to the **Storage Account** associated with the packet capture.
    
    ✋
    
-   6.2
    
    Open the **Container** named `network-watcher-rg`.
    
    ✋
    
-   6.3
    
    Locate the `.cap` file under the folder `packetcapture`.
    
    ✋
    
-   6.4
    
    Download the `.cap` file to your local machine.
    
    ✋
    

### Step 7: Analyze the Capture File

-   7.1
    
    Install **Wireshark** (an open-source packet analysis tool) if not already installed.
    
    ✋
    
-   7.2
    
    Open Wireshark and load the `.cap` file:
    
    ✋
    
-   Click **File** > **Open**.
-   Select the downloaded `.cap` file.
-   7.3
    
    Analyze the data:
    
    ✋
    
-   View the **Source IP** and **Destination IP** addresses.
-   Inspect TCP packets and other details.

### Step 8: Clean Up

-   8.1
    
    Navigate back to the **Packet Capture** section in **Network Watcher**.
    
    ✋
    
-   8.2
    
    Delete the completed packet capture session.
    
    ✋
    
-   8.3
    
    Optionally, delete the associated storage account if no longer needed.
    
    ✋
    

* * *

### **Additional Notes:**

-   **Timeout Configuration:** Packet capture sessions have a timeout in seconds (default is 18 minutes).
-   **Understanding IPs:** The private IP (e.g., `10.0.0.4`) is assigned to the VM within Azure, while the public IP (e.g., `208.x.x.x`) is the external-facing IP.
-   **Troubleshooting:** If the `.cap` file cannot be opened in a text editor (e.g., VS Code), use Wireshark to analyze the binary data.