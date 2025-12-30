## VM Monitoring

### Step 1: Create Virtual Machines

- 1.1
    
    Go to **Subscriptions** → **Resource providers**.
    
    ✋
    
- Register **Microsoft.AlertsManagement**
- Register **Microsoft.Insights**
- 1.2
    
    Search for **Virtual Machine**, +Create Virtual Machine
    
    ✋
    

#### 1st Virtual Machine

- Resource group: `dax`
- VM name: `curzon-dax`
- Region: **East US**
- Availability zone: 1
- Image: **Ubuntu Server 22.04 LTS - Gen2** (current recommended LTS)
- Size: Standard_B1ls
- Authentication: Password, Username: `dax`, Password: `Testing123456`
- Review + Create

#### 2nd Virtual Machine

- Same resource group: `dax`
- VM name: `jadzia-dax`
- Image: **Ubuntu Server 22.04 LTS - Gen2**
- Size: Standard_B1ls
- Authentication: Password (same as above)
- On **Management** tab → **Enable Azure Monitor** (uses AMA by default).
- Review + Create

#### 3rd Virtual Machine

- Resource group: `dax`
- VM name: `lela-dax`
- Image: **Windows Server 2022 Datacenter - Gen2** (updated, 2019 is older but still works if needed)
- Size: Standard_D2s_v3
- Authentication: Password (same as above)
- Review + Create

### Step 2: Monitoring with Azure Monitor & AMA

- 2.1
    
    Search for **Azure Monitor** → **Data Collection Rules**
    
    ✋
    
- +Create → Assign to your resource group `dax`
- Add your VMs (curzon-dax, jadzia-dax, lela-dax)
- Select metrics + performance counters (CPU, Memory, Disk)
- Destination: **Log Analytics Workspace**
- 2.2
    
    Create a **Log Analytics Workspace**:
    
    ✋
    
- Name: `dax-logs`
- Region: East US
- Link it to your **Data Collection Rule**
- 2.3
    
    Go to each VM → **Insights (Preview)**.
    
    ✋
    
- Confirm performance data and logs are flowing via AMA.

### Step 3: Azure Update Manager

- 3.1
    
    Search for **Update Manager** in the portal
    
    ✋
    
- 3.2
    
    Select resource group `dax` → Add all your VMs
    
    ✋
    
- 3.3
    
    Enable automatic assessment and patching
    
    ✋
    
- 3.4
    
    Use **Schedules** to test compliance reporting
    
    ✋
    

### Step 4: Logs & Metrics Demo

- 4.1
    
    Go to your **Log Analytics Workspace (`dax-logs`)**
    
    ✋
    
- 4.2
    
    Open **Logs** and try queries such as:
    
    ✋
    

```
Perf
| where ObjectName == "Processor"
| summarize avg(CounterValue) by bin(TimeGenerated, 5m)
```

- 4.3
    
    Try VM availability query:
    
    ✋
    

```
Heartbeat
| summarize Count = count() by bin(TimeGenerated, 5m), Computer
```

- 4.4
    
    Create an **Alert Rule** from Azure Monitor → Metrics
    
    ✋
    
- Metric: **Percentage CPU**
- Condition: >80% for 5 minutes
- Action: Email notification

### Step 5: Stress Test VM

- 5.1
    
    Copy the Public IP of `jadzia-dax`
    
    ✋
    
- 5.2
    
    Open **Cloud Shell (Bash)** → connect:
    
    ✋
    

```
ssh dax@<your_public_ip>
```

Password: `Testing123456`

- 5.3
    
    Install stress tool:
    
    ✋
    

```
sudo apt update
sudo apt install stress-ng -y
```

- 5.4
    
    Run load test:
    
    ✋
    

```
stress-ng --cpu 1 --vm 1 --vm-bytes 256M --timeout 60s
```

- 5.5
    
    Observe **Metrics in Azure Monitor** updating in real-time.
    
    ✋
    

### Cleanup

- Delete resource group `dax` after testing.

### Key changes:

- Replaced **Update Management (Automation Account)** with **Update Manager**.
- Replaced **Log Analytics agent** with **Azure Monitor Agent (AMA) + DCRs**.
- Removed **guest-level monitoring** references.
- Updated OS images (Ubuntu 22.04, Windows Server 2022).