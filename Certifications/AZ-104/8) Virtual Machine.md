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