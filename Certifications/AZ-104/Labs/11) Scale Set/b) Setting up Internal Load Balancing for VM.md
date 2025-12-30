## Internal Load Balancer for VMs Lab Notes

### Overview

This lab guides you through building and configuring two VMs, setting up a virtual network and subnet, and deploying an **Internal (Standard SKU) Load Balancer** with HTTP load‑balancing and health monitoring. It’s streamlined for clarity and aligns with Azure's current best practices.

### Step 1: Create Two VMs

- 1.1
    
    In the Azure portal, search for **Virtual machine**, then click **Create → Azure Virtual Machine**.
    
- 1.2
    
    Configure:
    
- **Resource group**: `exampro-rg` (create new)
- **VM names**: `exampro-vm` and `exampro-vm2`
- **Image**: Windows Server 2019 Datacenter Gen2
- **Size**: Standard_B1s
- **Admin credentials**: user `exampro1`, password `Testing123456`
- **Inbound ports**: HTTP (80), SSH (22), RDP (3389)
- 1.3
    
    Click **Review + create**, review, then **Create**. Repeat for the second VM.
    

### Step 2: Virtual Network & Subnet

- 2.1
    
    Search for **Virtual Networks** in the portal.
    
- 2.2
    
    Select the VNet automatically created (likely named `exampro-vm-vnet`).
    
- 2.3
    
    Go to **Subnets → + Add Subnet**:
    
- Name: `MySubnet`
- Address range: `10.0.2.0/24`
- (Optionally attach an NSG, e.g., `exampro-vm-nsg`)
- 2.4
    
    Save your configuration.
    

### Step 3: Create an Internal Load Balancer

- 3.1
    
    Search for **Load Balancers**, click **Add** to start creation.
    
- 3.2
    
    Under **Basics**:
    
- **Name**: `MyLoadBalancer`
- **SKU**: Standard (recommended for production environments) ([ScholarHat][1], [Stack Overflow][2], [SIOS Technology Portal][3], [Microsoft Learn][4])
- **Type**: Internal
- **Tier**: Regional
- **Resource group/region**: match existing ones
- 3.3
    
    In **Frontend IP configuration**:
    
- Add a frontend named `MyFrontendIP`
- Assign it to the `MySubnet` subnet
- 3.4
    
    In **Backend pool**:
    
- Create `MyBackendPool`
- Add both VMs’ IP configurations to this pool
- 3.5
    
    Click **Review + create**, then **Create**.
    

### Step 4: Configure Load Balancing Rule & Health Probe (HTTP Only)

**This streamlined lab includes just one rule for HTTP (80), focusing on common app traffic.**

- 4.1
    
    Go to your load balancer → **Load balancing rules → + Add**.
    
- 4.2. [ ] Configure:
- **Name**: `MyHTTPRule`
- **Frontend IP**: `MyFrontendIP`
- **Protocol**: TCP
- **Port**: 80 (frontend and backend)
- **Backend pool**: `MyBackendPool`
- **Health probe**: Create new:
    
- Name: `MyHealthProbe`
    
- Protocol: HTTP, Port: 80, Path: `/`, Interval: default (e.g., 5s)
    
- **Session persistence**: None (default)
    
- **Idle timeout**: default (e.g., 4 minutes)
    
- **TCP reset**: Enabled (recommended) ([Azure Docs][5], [Microsoft Learn][6], [pulumi][7])
    
- **Floating IP**: Disabled
    
- 4.3 [ ] Click **Add**.
    

### Why We Simplified

#### No HTTPS (443) Rule

- HTTPS (443) is only needed if encrypted traffic is required. HTTPS termination is **not supported** by Azure Load Balancer—it passes it through (Layer 4). Use Application Gateway if you need SSL termination or Layer‑7 features. ([Azure Docs][8])

#### No Load Balancing for Admin Ports

- SSH and RDP are for administrative access, not scalable application traffic. If remote access is needed, use **Inbound NAT rules** (for specific VM access) or **Azure Bastion**, not load balancing rules. ([Microsoft Azure][9])

#### Uniqueness of Rules

- Azure ensures each rule’s combination of **frontend IP + protocol + port** is unique to avoid conflicts. ([Microsoft Learn][10])

#### Future Forward: HA Ports Option

- In complex scenarios (e.g., network virtual appliances or many ports), Azure supports **High Availability (HA) Ports** – a single rule that balances all ports and protocols (set port = 0, protocol = All). ([Microsoft Learn][6])

### Section 5: (Optional) Adding Rules Post-Creation

If needed, you can always revisit the Load Balancer to add more rules—like inbound NAT rules for SSH/RDP or additional app-specific ports—via the **Load balancing rules** blade. ([Microsoft Azure][9]) Use NAT rules for port forwarding rather than balancing.