## Creating and Configuring Network Security Groups

### Summary

The lab focuses on the creation and configuration of network security groups in Azure. Users learn to create a virtual network, a network security group, and a virtual machine. The main objective is to configure the network security group settings to allow access to the virtual machine.

### Section 1: Create a Virtual Network

-   1.1
    
    On the Search Tab, search for Virtual Networks, and click on Virtual Networks.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+1.png)

-   1.2
    
    Click on + Create to create a Virtual Network. Provide the resource group, resource name, and region. We can use the default settings for IP addresses and subnets.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+2.png)

-   1.3
    
    Click on Review + Create, then click Create.
    
    ✋
    

### Section 2: Create a Network Security Group

-   2.1
    
    On the Search Tab, search for Network Security Group, and click on Network Security Groups.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+1.png)

-   2.2
    
    Click on + Create to create a Network Security Group. Provide the resource group, resource name, region, etc.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+2.png)

-   2.3
    
    Click on Review + Create, then click Create.
    
    ✋
    

### Section 3: Create a Virtual Machine

-   3.1
    
    In the Search Tab, search for "Virtual machine". And Click on **Virtual machine**. You can also use the left-hand menu/blade.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+3.png)

-   3.2
    
    Click on + Create. Then click on Azure Virtual Machine.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+4.png)

-   3.3
    
    Enter in the Settings and parameters.
    
    ✋
    
-   Create a new resource group: exampro-rg
-   Virtual machine name: **exampro-vm**
-   Image: Windows Server 2019 Datacenter - x64 Gen2
-   Size: \`\`\`Standard\_B1s
-   **username**: exampro | **password**: Testing123456
-   **Select inbound ports**: RDP (3389)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+5.png)

-   3.4
    
    Click on Networking. Ensure that your VM is placed in the **exampro-vnet** that you created in **Section 1**. You can leave the default subnet settings. And the Public IP can remain default.
    
    ✋
    
-   NIC networking settings: **Advanced** | Select the **network security group** you created on **Section 2**: **exampro-nsg**

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+6.png)

-   3.5
    
    Click Review and Create. Review your settings and click "Create" to create the VM.
    
    ✋
    

### Section 4: Configure the Network Security Group

-   4.1
    
    Go to the Virtual Machine, Click on the "Connect" blade, and download the RDP File.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+7.png)

-   4.2
    
    Open the RDP File and Click on Connect
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+8.png)

-   4.3
    
    You should get receive an error, noting that you can't connect to the remote computer.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+9.png)

-   4.4
    
    Navigate to the Network Security Group - exampro-nsg that you created earlier. You can also go to the "Networking" blade of the Virtual Machine.
    
    ✋
    
-   4.5
    
    Under settings, Click on Inbound security rules. Then Click on "+ Add".
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+10.png)

-   4.6
    
    Enter the information required for the inbound security rule.
    
    ✋
    
-   Source: Any
-   Source port ranges: \*
-   Destination: Any
-   Service: Custom
-   **Destination port ranges**: 3389
-   **Protocol**: TCP
-   Action: **Allow**
-   Priority: 100 (The lower the number, the higher the priority)
-   Name: We can leave this default as: AllowAnyCustom3389inbound

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+11.png)

-   4.7
    
    Click on Add to add the inbound security rule.
    
    ✋
    

### Section 5: Test the Network Security Group

-   5.1
    
    Navigate back to the VM. Click on the Connect tab, and download the RDP file again. Or you can use the same RDP file you downloaded earlier.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+12.png)

-   5.2
    
    Open the RDP file. This time, you should be able to connect to the VM after adding the inbound security rule.
    
    ✋
    
-   5.3
    
    Enter the credentials you created for you the VM. Click OK.
    
    ✋
    
-   Username: exampro | password: Testing123456

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+13.png)

-   5.4
    
    After successfully connecting to the VM, you can close the VM. This proves that we can connect to the VM with the inbound security rule for the Network Security Group.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Network+Security+Group/Network+Security+Group+-+14.png)

-   5.5
    
    You may delete and clean up the resources you created.
    
    ✋