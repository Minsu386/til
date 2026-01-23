## **Lab Notes: Debugging NSG with Diagnostic Tools**

### **Objective**

Learn how to use Azure's NSG diagnostic tools, test NSG rules, and troubleshoot network connectivity issues.

### Step 1: Navigate to the Virtual Machine

-   1.1
    
    Go to the **Azure Portal**.
    
    ✋
    
-   1.2
    
    In the left-hand menu, search for **"Virtual Machines"** and select your target virtual machine (VM).  
    
    ✋
    
-   For this guide, the VM is named **Risa**.

### Step 2: Launch NSG Diagnostics

-   2.1
    
    In the VM menu, locate **Network Watcher**.  
    
    ✋
    
-   If it’s not enabled, enable Network Watcher in your region.  
    
-   2.2
    
    Under **Network Watcher**, select **NSG Diagnostic**.
    
    ✋
    

### Step 3: Configure NSG Diagnostics

-   3.1
    
    Under the **NSG Diagnostic** tool:  
    
    ✋
    
-   **Virtual Machine**: Select your VM (e.g., **Risa**).  
    
-   **Protocol**: Choose **TCP**.  
    
-   **Direction**: Select **Inbound**.  
    
-   **Source IP**: Enter your **public IP address** (your IP).  
    
-   **Destination IP**: It is pre-filled with the VM's **Public IP Address**.  
    
-   **Port**: Enter **80** (HTTP).  
    
-   3.2
    
    Click **Check**.
    
    ✋
    

### Step 4: Verify the Results

-   4.1
    
    Observe the results:  
    
    ✋
    
-   **Traffic Allowed**: NSG rules permit traffic.  
    
-   **Traffic Denied**: NSG rules block traffic.  
    
-   4.2
    
    Click into the **detailed results** for a breakdown of security rules and match conditions.
    
    ✋
    

### Step 5: Modify NSG Rules

-   5.1
    
    Navigate to the **Network Security Groups** for your VM:  
    
    ✋
    
-   Go to the **Azure Portal** > **Network Security Groups**.  
    
-   5.2
    
    Locate the **Inbound Rules**.
    
    ✋
    
-   5.3
    
    Change the **port rule** for testing purposes:  
    
    ✋
    
-   Example: Change **Port** from `80` to `8080` (to block expected traffic).  
    
-   5.4
    
    Click **Save** to apply changes.
    
    ✋
    

### Step 6: Re-Test NSG Diagnostics

-   6.1
    
    Go back to **Network Watcher** > **NSG Diagnostics**.
    
    ✋
    
-   6.2
    
    Re-enter the following:
    
    ✋
    
-   **Source IP**: Your public IP.  
    
-   **Port**: **80**.  
    
-   6.3
    
    Click **Check**.
    
    ✋
    
-   6.4
    
    Verify the results:  
    
    ✋
    
-   Traffic should now show **Denied**.  
    
-   Click into the **detailed report** to see why traffic is denied (e.g., default rule blocks it).

### Step 7: Test Connection with Connection Troubleshoot

-   7.1
    
    Go to **Network Watcher** > **Connection Troubleshoot**.
    
    ✋
    
-   7.2
    
    Under **Connection Troubleshoot**:
    
    ✋
    
-   **Source**: Your VM (**Risa**).  
    
-   **Destination IP**: VM’s public IP.  
    
-   **Protocol**: TCP.  
    
-   **Port**: **80**.  
    
-   7.3
    
    Click **Check**.
    
    ✋
    
-   7.4
    
    Observe the result:  
    
    ✋
    
-   Network blocked: Default NSG rules block inbound traffic.  
    
-   Less detailed than the NSG Diagnostic tool.

### Step 8: Revert NSG Changes

-   8.1
    
    Return to the **Network Security Groups**:
    
    ✋
    
-   Edit the **Inbound Rule** back to allow traffic on **Port 80**.  
    
-   Set **Destination Port** to `*` or `80`.  
    
-   8.2
    
    Save changes.
    
    ✋
    

### Step 9: Validate Changes

-   9.1
    
    Use **NSG Diagnostic** again:
    
    ✋
    
-   Test the same configuration: **Port 80**, **Inbound**, TCP.  
    
-   9.2
    
    Verify that traffic is now **Allowed**.  
    
    ✋
    
-   9.3
    
    Use **Connection Troubleshoot** from the VM to confirm successful connectivity.
    
    ✋
    

#### Troubleshooting Notes

-   **Propagation Delay**: Azure NSG rule changes may take a few minutes to propagate.
-   **Re-run Tests**: If tests fail unexpectedly, re-run the diagnostic tool after a short wait.
-   **Detailed View**: Use the NSG Diagnostics tool for more detailed reports compared to the simpler Connection Troubleshoot.

#### Outcome

By the end of this lab, you should be able to:

1.  Diagnose NSG rules blocking traffic.  
    
2.  Modify NSG rules and verify their effect.  
    
3.  Use both **NSG Diagnostics** and **Connection Troubleshoot** for debugging.