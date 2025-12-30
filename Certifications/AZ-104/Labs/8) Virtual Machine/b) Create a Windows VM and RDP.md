## Create a Windows VM and RDP

**Section 1 - Create a Windows VM and RDP**

- 1.1
    
    Search for Virtual Machine, +Create Virtual Machine
    
    ✋
    
- Create a new resource group: cardassia
- Virtual machine name: cardassia
- Image: Windows Server 2022 Datacenter: Azure Edition - Gen2
- Size: Standard_B2s, username: azureuser and password: Testing123456
- Select inbound ports: RDP (3389), Disks: Standard SSD

Click Review and Create

- 1.2
    
    Go to the virtual machine: cardassia, Click on Connect, Click on the **RDP** tab, Download the **RDP File**, Enter in credentials username: azureuser123456 and password: Testing123456, Hit Ok, Click Yes
    
    ✋
    
- 1.3
    
    You should have access to the Windows VM, after you are finished, delete resource group: cardassia
    
    ✋
    

### Reference

[Quickstart: Create a Windows virtual machine in the Azure portal](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)