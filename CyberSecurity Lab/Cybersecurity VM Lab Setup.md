# Phase 1
----

#### **Prerequisites**

1. Ensure you have **Proxmox** installed and running.
2. Download the required ISO images:
    - **pfSense** Firewall
    - **Kali Linux**
    - **Ubuntu Desktop** and **Ubuntu Server**
3. Set up network design:
    - **VLAN 10**: Security Tools
    - **VLAN 20**: Windows Environment
    - **VLAN 30**: Docker Containers
    - **VLAN 40**: Vulnerable Machines

---

### **Step 1: Set Up pfSense Firewall**

1. **Create pfSense VM**:
    - Go to **Proxmox > Create VM**.
    - Set **ID**: `2011`, Name: `prod-firewall`.
    - Select the **pfSense ISO**.
    - For Network:
        - Interface 1: `vmbr0` (WAN)
        - Interface 2: Add a new Linux Bridge: `vmbr2` for LAN.
    - Allocate **32 GB storage**.

2. **Configure pfSense**:
    - Start the VM and follow the prompts.
    - **Network Setup**:
        - WAN: `vtnet0`
        - LAN: `vtnet1`
    - Set LAN IP:
        - **IP**: `10.10.1.254/24`
        - Enable DHCP: Start: `10.10.1.50`, End: `10.10.1.100`.
    - **Reboot**.

3. **Create VLANs**:
    - Go to **Interfaces > VLANs**:
        - VLAN 10: Security Tools (10.10.10.0/24)
        - VLAN 20: Windows Environment (10.10.20.0/24)
        - VLAN 30: Docker (10.10.30.0/24)
    - Assign VLANs to `vmbr2` and configure static IPs.

4. **Firewall Rules**:
    - Go to **Firewall > Rules**:
        - Copy LAN rule (Allow All) to VLAN 10, 20, and 30.
        - Update **Source** to match each VLAN subnet.

5. **Enable DHCP for VLANs**:
    - Go to **Services > DHCP Server**:
        - VLAN 10: `10.10.10.50 - 10.10.10.100`
        - VLAN 20: `10.10.20.50 - 10.10.20.100`
        - VLAN 30: `10.10.30.50 - 10.10.30.100`

---

### **Step 2: Deploy Kali Linux (Attack Machine)**

1. **Create VM**:
    - **ID**: `202`, Name: `prod-kali`.
    - Select **Kali Linux ISO**.
    - **Storage**: 120 GB.
    - **RAM**: 8 GB.
    - Assign to VLAN 10 (`vmbr2`).

2. **Install Kali**:
    - Follow setup prompts.
    - **Username/Password**: `student`/`your-password`.
    - Verify connectivity:
        ```bash
        ping 10.10.1.254
        ```

---

### **Step 3: Set Up Ubuntu Server (Docker Host)**

1. **Create VM**:
    - **ID**: `203`, Name: `prod-docker`.
    - Select **Ubuntu Server ISO**.
    - **Storage**: 100 GB.
    - **RAM**: 16 GB.
    - Assign to VLAN 30.

2. **Install Ubuntu Server**:
    - Enable **OpenSSH** during installation.
    - Reboot and verify the IP (e.g., `10.10.30.50`).

3. **Install Docker**:
    - SSH into the Ubuntu server:
        ```bash
        sudo apt-get update
        sudo apt-get remove docker docker-engine docker.io containerd runc
        sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
        sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
        sudo apt-get update
        sudo apt-get install docker-ce
        sudo systemctl start docker
        sudo systemctl enable docker
        ```

4. **Verify Docker**:
    ```bash
    sudo docker run hello-world
    ```

5. **Install Portainer**:
    - Pull the Portainer image and run:
        ```bash
        sudo docker volume create portainer_data
        sudo docker run -d -p 9000:9000 --name=portainer --restart=always \
          -v /var/run/docker.sock:/var/run/docker.sock \
          -v portainer_data:/data portainer/portainer-ce
        ```
    - Access Portainer at: `http://10.10.30.50:9000`.

---

### **Step 4: Set Up Windows Active Directory**

1. **Create Windows Server VM**:
    - **ID**: `204`, Name: `prod-ad`.
    - Select **Windows Server 2022 ISO**.
    - Assign to VLAN 20.
    - Configure:
        - **Roles**: Active Directory Domain Services (AD DS).
        - **IP**: `10.10.20.10`.

2. **Add Windows 10 and 11 Clients**:
    - Create two VMs for Windows 10 and 11.
    - Join both machines to the domain.

---

### **Step 5: Add Vulnerable Machines**

1. **Download Vulnerable ISOs**:
    - Examples: **Metasploitable 2**, **DVWA**, **OWASP BWA**.
    - Assign to VLAN 40.

2. **Create VMs**:
    - Configure static IPs within the `10.10.40.0/24` range.

---

### **Step 6: Verify Connectivity**

1. From Kali Linux:
    - Ping:
        ```bash
        ping 10.10.1.254
        ping 10.10.30.50
        ping 10.10.20.10
        ```
    - SSH into Ubuntu Server.

2. Verify DNS and DHCP functionality.

---

### **Summary**

You have now:

1. Configured a **pfSense** firewall and multiple VLANs.
2. Deployed:
    - **Kali Linux** (attack machine).
    - **Ubuntu Server** with Docker and Portainer.
    - **Windows Server** with Active Directory.
    - Vulnerable machines for testing.
3. Verified connectivity across all environments.

This lab is now ready for **hands-on practice** with cybersecurity tools like Nessus, Security Onion, and more.

---

# Phase 2
----

### **Episode 2: Building Vulnerable Machines for the Cybersecurity Lab**

Welcome back to _Episode 2_ of the _Ultimate Cybersecurity Lab Project_. In the previous episode, we:

1. Built the **PFSense Firewall** and configured VLANs, DHCP, and firewall rules.
2. Set up **Kali Linux** and **Ubuntu VM** with Docker and Portainer installed.

---

### **Part 1: Setting Up Metasploitable 2 VM**

1. **Create the VM in Proxmox**:
    ```bash
    ssh root@192.168.0.14
    cd /var/lib/vz
    mkdir 204 && cd 204
    wget <Metasploitable2_Link>
    unzip Metasploitable2.zip
    qemu-img convert -f vmdk -O qcow2 Metasploitable.vmdk metasploitable.qcow2
    nano /etc/pve/qemu-server/204.conf
    ```

---

### **Part 2: Deploying Containers with Portainer**

1. **MACVLAN Setup**:
    ```bash
    ssh user@10.10.10.135
    ip a
    ```

2. **Deploy Containers**:
    - **BWA**:
        ```bash
        docker run -d --name prod_bwa --network vlan30 <bwa_image>
        ```
    - **DVWA**:
        ```bash
        docker run -d --name prod_dvwa --network vlan30 <dvwa_image>
        ```
    - **WebGoat**:
        ```bash
        docker run -d --name prod_webgoat --network vlan30 <webgoat_image>
        ```

---

### **What’s Next?**

Now that we’ve built our **vulnerable machines**, we’ll move on to **deploying security tools** like:

- **Wazuh**
- **Nessus**
- Other scanning tools.


# Phase 3

# Ultimate SEAR Security Lab Project: Episode 3

Welcome back to the **Ultimate SEAR Security Lab Project**! Here's a quick recap:

- **Episode 1:** We built the pfSense firewall, Kali Linux instance, Docker server, and Active Directory.
- **Episode 2:** We deployed several vulnerable machines, including Metasploitable2 and various vulnerable Docker containers.
- **Episode 3 (Current):** We’ll build **Wazuh** (SIEM and XDR tool) and **Nessus** (vulnerability scanner).

If you’re new here, I recommend watching the earlier episodes, as each builds on the previous one.

---

## Wazuh Installation

### Step 1: Build the Wazuh VM

1. **VM Setup:**
    
    - Use **Ubuntu** as the base image.
    - Assign **ID: 205**, set the name to `prod-wazuh`, and allocate 160 GB storage for logs.
    - Configure 4 vCPUs, 8 GB RAM, and assign a static IP (e.g., `10.1.1.51`).
2. **Ubuntu Build Process:**
    
    - Set up a static IP:
        - Subnet: `10.10.10/24`
        - Gateway: `10.1.1.254`
        - DNS: Use your firewall IP (`10.1.1.254`) and Google DNS.
    - Complete the setup, create user credentials, install OpenSSH, and reboot.
3. **Update the OS:**
    
    bash
    
    Copy code
    
    `sudo apt update && sudo apt upgrade`
    

---

### Step 2: Install Wazuh

1. **Run the installation command:**  
    Copy the one-liner command from the Wazuh documentation and execute it.
2. **Access the Wazuh web interface:**
    - Open the browser and navigate to `https://10.1.1.51`.
    - Log in using the credentials provided during installation.

---

### Step 3: Configure Agents

#### (A) **Kali Linux Agent**

1. On the Kali Linux machine:
    
    - Elevate to root:
        
        bash
        
        Copy code
        
        `sudo -i`
        
    - Execute the installation commands:
        
        bash
        
        Copy code
        
        `wget <agent-repo-url> sudo apt update sudo apt install wazuh-agent`
        
    - Configure the agent to point to the Wazuh server (`10.1.1.51`).
    - Start the agent.
2. Verify in the Wazuh web interface:
    
    - Go to **Agents** and ensure the Kali Linux agent is connected.

#### (B) **Docker Server Agent**

1. SSH into the Docker server and repeat the same process as above:
    
    - Install the agent and configure it to point to the Wazuh server.
    - Enable and start the agent.
2. Enable Docker container monitoring:
    
    - Install the Docker listener on the Wazuh server.
    - Update the Wazuh agent config file with Docker monitoring settings.

---

### Step 4: pfSense Firewall Integration

1. **Enable SSH on pfSense:**
    
    - Log in to the pfSense web interface, go to **System > Advanced**, and enable Secure Shell.
2. **Install Wazuh Agent:**
    
    - Enable FreeBSD package management.
    - Install the Wazuh agent using the appropriate version.
3. **Send Logs to Wazuh:**
    
    - Configure pfSense to forward logs (e.g., syslogs) to the Wazuh server.
    - Create a Wazuh group and rules for pfSense-specific logs.
4. **Verify:**
    
    - Check the Wazuh interface to ensure logs and events are populating correctly.

---

## Next Steps: Deploy Nessus

The next tool to deploy in this lab is **Nessus**, a vulnerability scanner. This involves creating another VM and performing similar setup steps. Stay tuned for detailed instructions in the next segment!

---

Let me know if you’d like more details on any part!

4o

##### You said:

change the last response to be markdown capatible

###### ChatGPT said:

ChatGPT

Here’s the response formatted for Markdown compatibility:

---

## Markdown-Compatible Version

### Overview of the Video

In this video, we continue building our **Ultimate Security Lab Project**. Here's a quick summary of the previous episodes:

- **Episode 1**: Built the pfSense firewall, Kali Linux instance, Docker server, and AD container.
- **Episode 2**: Deployed vulnerable machines, including Metasploitable2 and various vulnerable containers.
- **Episode 3 (This Episode)**: Focused on deploying **Wazuh** (SEIM/XDR tool) and **Nessus** (vulnerability scanner).

If you're new, watch the previous episodes to follow the progression.

---

### Building the Wazuh VM

1. **VM Setup**:
    
    - Created a new Ubuntu VM with:
        - **ID**: 205
        - **Name**: prod-wazuh
        - **Storage**: 160GB (for log storage)
        - **vCPUs**: 4
        - **RAM**: 8GB (8192MB)
        - **Network**: VLAN 1 (Static IP: `10.1.1.<next-available>`)
2. **Configuration**:
    
    - Set static IP (`10.1.1.51`), gateway (`10.1.1.254`), and name servers (local firewall + Google DNS).
    - Completed the Ubuntu installation, set up SSH, updated the system, and prepared for Wazuh installation.
3. **Installing Wazuh**:
    
    - Ran a single command to install Wazuh Server.
    - Logged into the Wazuh web interface and configured it.

---

### Deploying Wazuh Agents

1. **Kali Linux Agent**:
    
    - Installed the Wazuh agent using provided commands.
    - Configured the agent to communicate with the Wazuh server (`10.1.1.51`).
    - Validated the agent connection in the Wazuh web interface.
2. **Docker Server Agent**:
    
    - Repeated the installation process on the Docker server.
    - Enabled the **Wazuh Docker Listener** to monitor container activity.
3. **pfSense Firewall Agent**:
    
    - Enabled SSH and FreeBSD package manager.
    - Installed the Wazuh agent and configured it to forward logs to the server.
    - Created custom rules and decoders in Wazuh to process firewall logs.

---

### Monitoring and Logs

1. **Agent Validation**:
    
    - Verified active agent connections in the Wazuh dashboard.
    - Checked logs from the Kali Linux instance, Docker server, and pfSense firewall.
2. **pfSense Log Customization**:
    
    - Enabled firewall drop events (disabled by default).
    - Added new rules and decoders to improve log visibility in Wazuh.

---

### Next Steps

With Wazuh fully deployed and integrated, the next task is to install **Nessus**. Stay tuned for the upcoming episode, where we'll:

- Deploy Nessus as a VM.
- Configure it for vulnerability scanning.