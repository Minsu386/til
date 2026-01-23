## Capture Virtual Network Flow Logs Lab Notes

### Why Virtual Network Flow Logs?

-   **NSG Flow Logs are retiring**:
    -   No new creation allowed after **June 30, 2025**.
    -   Full retirement on **September 30, 2027**.
-   **Virtual Network Flow Logs (VNet Flow Logs)** are the replacement:
    -   Provide the same flow telemetry (ingress/egress, allow/deny).
    -   More scalable and future-proof.
    -   Integrate directly with **Traffic Analytics** and **Log Analytics**.

### Prerequisites

-   An existing **Virtual Network (VNet)** with **subnets and NSGs** attached.
-   Permission to create **Storage Accounts** and **Log Analytics Workspaces**.

### Step 1: Navigate to Virtual Network Flow Logs

-   1.1
    
    In the **Azure portal**, search for **Network Watcher**.
    
    ✋
    
-   1.2
    
    Under **Monitoring**, select **Flow logs**.
    
    ✋
    
-   1.3
    
    Choose **Virtual Network Flow Logs** instead of NSG Flow Logs.
    
    ✋
    

### Step 2: Create a Virtual Network Flow Log

-   2.1
    
    Click **\+ Create**.
    
    ✋
    
-   2.2
    
    Fill in the details:
    
    ✋
    
-   **Subscription** and **Resource group** → choose your existing ones.
-   **Region** → must match your Virtual Network.
-   **Flow log name** → e.g., `vnet-flowlog-demo`.
-   **Virtual Network** → select the VNet you want to monitor.

### Step 3: Configure Storage and Retention

-   3.1
    
    Select a **Storage Account** (create a new one if needed).
    
    ✋
    
-   Use only lowercase letters/numbers for naming.
-   Example: `vnetflowstorage123`.
-   **Standard LRS** is sufficient.
-   3.2
    
    Optionally, configure **Retention (days)** for log storage.
    
    ✋
    

### Step 4: Enable Traffic Analytics

-   4.1
    
    Under **Traffic Analytics**, click **Enable**.
    
    ✋
    
-   4.2
    
    Select an existing **Log Analytics Workspace**, or create a new one:
    
    ✋
    
-   Example: `vnet-flow-logs-workspace`.
-   4.3
    
    Choose a **data collection interval**:
    
    ✋
    
-   Default: **1 hour**
-   For lab/demo: **10 minutes** (more granular).

### Step 5: Deploy and Verify

-   5.1
    
    Click **Review + Create** → then **Create**.
    
    ✋
    
-   5.2
    
    Wait for the deployment to finish.
    
    ✋
    
-   5.3
    
    Return to **Flow logs** and confirm your new VNet Flow Log is listed.
    
    ✋
    

### Step 6: Access and Analyze Logs

#### Option A: From Storage Account

-   1\. Go to your **Storage Account** → **Blob containers**.
-   2\. Drill down through folders until you reach **JSON log files**.
-   3\. Download and format the file with a tool like Pretty JSON.
-   4\. Logs will show:
    -   **Inbound/Outbound traffic**
    -   **Allow/Deny actions**
    -   **Packet/Byte counts**

#### Option B: From Traffic Analytics

-   1\. In **Network Watcher**, open **Traffic Analytics**.
-   2\. Use the built-in dashboards to visualize:
    -   Top talkers (IP addresses sending/receiving the most traffic).
    -   Allowed vs denied flows.
    -   Traffic volume over time.

### Step 7: (Optional) External Integrations

-   Export flow logs to third-party tools for richer analysis:
    -   **Grafana**
    -   **Elastic Stack (ELK)**
    -   **Graylog**

### Summary

You’ve now configured **Virtual Network Flow Logs** in Azure, the recommended successor to NSG Flow Logs. These logs provide detailed network traffic telemetry and integrate seamlessly with Azure Traffic Analytics for visualization.