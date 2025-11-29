**Azure Virtual Machine**: Allows you to create Linux and Windows virtual machines
The size of the virtual machine is determined by the image
- The image defines the combination of vCPUs, Memory and Storage Capacity

The current limit on a per subscription basis is **20 VMs per region**.
Azure VMs are billed at an **HOURLY** rate
A single instance VMs has an availability of 99.9% (when all storage disk are premium)
Two instances deployed in Availability Set will give you 99.95% availability
You can attach multiple Manged Disk to your Azure Vms
When you launch an Azure VM other networking components will be either created or associated to your VM
- Network Security Group (NSG), Network Interface (NIC), Public IP Address, VNet

You can **Bring your own Linux** by creating a Linux Virtual Hard Disk (VHD)

Azure VMs come in variety of sizes that are also optimized for specific use cases.
- General Purpose, Compute Optimized, Memory Optimized, Storage Optimized, GPU, High Performance Compute

**Azure Compute Unit (ACU)** provides a way of comparing compute (CPU) performance across Azure SKUs
ACU is currently standardized on a **Small (Standard_A1)**  VM with the value of 100
All other SKUs then represent approximately how much faster that SKU can run a standard benchmark

You can install the **Azure Mobile App**, and you can monitor your VMs on the go

**Hyper-V** is Microsoft's Hardware Virtualization product.
- It lets you create and run a software version of a computer. 

There are two generations of Hyper-V:
- Gen 1 - Support most guest operating system
- Gen 2 - Support most 64-bit versions of windows and more current version of Linux and FreeBSD OS
**Hyper-V VMs** are packaged into Virtual Hard Disk formats: VHD or VHDX files

There are 3 ways to connect to VM
**Secure Shell (SSH)** connect via terminal, or SSH client ie PuTTy
- SSH happens on **Port 22** via TCP
- RSA Key Pairs are commonly used to authorize access

**Remote Desktop Protocol (RDP)** a GUI to connect to another computer over network
- This is how you can remotely connect to Windows Server via Virtual Desktop
- RDP happens on **Port 3389** via TCP and UDP

**Azure Bastion** connect using browser and the Azure Portal
- Support both SSH or RDP, useful when you only have browser like a chromebook or do not have permission to configure or install software

**Update Management** allows you to **manage and install OS updates and patches** for both **Windows & Linux** virtual machine that are deployed in Azure, on-prem, or in other cloud providers
- Update Management will perform a scan for update compliance
- A compliance scan is by default, **performed 12hrs for Win and 3 hrs Linux**
- It can take 30m to 6hr for dashboard to display updated data from managed computers. 