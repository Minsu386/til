### Lab Notes: Verify IP Flow Using Azure Network Watcher

#### Objective

Test and troubleshoot network connectivity for a Virtual Machine (VM) using Azure Network Watcher’s IP Flow Verify feature.

### Prerequisites

1.  An active Azure subscription.  
    
2.  A Virtual Machine (VM) deployed in Azure with a private IP address.  
    
3.  Network Watcher enabled in the region where the VM is deployed.  
    

### Step 1: Access Azure Network Watcher

-   1.1
    
    Go to the **Azure Portal**.  
    
    ✋
    
-   1.2
    
    In the search bar at the top, type and select **Network Watcher**.  
    
    ✋
    

### Step 2: Verify IP Flow

-   2.1
    
    In the **Network Watcher** menu, locate and select **IP Flow Verify** under **Network Diagnostic Tools**.  
    
    ✋
    
-   2.2
    
    The **IP Flow Verify** form will appear.  
    
    ✋
    

### Step 3: Configure IP Flow Verification

-   3.1
    
    **Resource Group**:  
    
    ✋
    
-   From the dropdown, select the resource group containing your Virtual Machine.  
    
-   3.2
    
    **Virtual Machine**:  
    
    ✋
    
-   From the dropdown, choose the specific VM you want to test.  
    
-   3.3
    
    **Network Interface**:  
    
    ✋
    
-   The Network Interface associated with the VM will be auto-populated.  
    
-   3.4
    
    **Protocol**:  
    
    ✋
    
-   Choose **TCP** or **UDP** depending on the traffic type you want to test.  
    
-   3.5
    
    **Local IP Address**:  
    
    ✋
    
-   This refers to the **private IP address** of your Virtual Machine.  
    
-   To find the VM’s private IP:  
    a. Navigate to the **Virtual Machine** in the Azure Portal.  
    b. In the **Overview** tab or under the **Networking** section, locate the **Private IP Address** (e.g., `10.0.0.4`).  
    
-   Copy and paste this private IP into the **Local IP Address** field.  
    
-   3.6
    
    **Remote IP Address**:  
    
    ✋
    
-   If testing from your local machine, determine your **public IP address**:  
    a. Open a browser and search for **"What's my IP"** in Google.  
    b. Copy the public IP address provided.  
    
-   Paste this public IP address into the **Remote IP Address** field.  
    
-   3.7
    
    **Port**:  
    
    ✋
    
-   Specify the **port number** you are testing. (e.g., `80` for HTTP traffic).  
    

### Step 4: Run the Verification Test

-   4.1
    
    Click **Check** or **Run** to initiate the IP flow test.  
    
    ✋
    
-   4.2
    
    Observe the results:  
    
    ✋
    
-   If connectivity works, you will see a **Success** message.  
    
-   If connectivity fails, Azure will provide details explaining why traffic is being blocked (e.g., Network Security Group rule).  
    

### Step 5: Analyze Results

-   If successful, the test confirms traffic can flow between the two IP addresses on the specified port and protocol.  
    
-   If unsuccessful, review the output to identify any issues. Common problems include:  
    -   NSG (Network Security Group) rules blocking traffic.  
        
    -   Incorrect configurations in the virtual network or firewall.  
        

#### **Example Recap:**

1.  VM Private IP: `10.0.0.4`  
    
2.  Public IP of Local Machine: `203.0.113.45` (example)  
    
3.  Port: `80`  
    
4.  Protocol: **TCP**  
    

#### **Notes:**

-   Use this process whenever you want to test whether network traffic is flowing to or from your Azure VM.  
    
-   Ensure the **Network Watcher** is enabled in the region where the VM resides.