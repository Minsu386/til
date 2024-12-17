
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
        - Ping the firewall LAN IP: `10.10.1.254`.

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
        
        bash
        
        Copy code
        
        `sudo apt-get update sudo apt-get remove docker docker-engine docker.io containerd runc sudo apt-get install apt-transport-https ca-certificates curl software-properties-common curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" sudo apt-get update sudo apt-get install docker-ce sudo systemctl start docker sudo systemctl enable docker`
        
4. **Verify Docker**:
    
    bash
    
    Copy code
    
    `sudo docker run hello-world`
    
5. **Install Portainer**:
    
    - Pull the Portainer image and run:
        
        bash
        
        Copy code
        
        `sudo docker volume create portainer_data sudo docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce`
        
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
        - Firewall LAN IP: `10.10.1.254`
        - Docker Host: `10.10.30.50`
        - Windows AD: `10.10.20.10`
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


# Phase 2
----
