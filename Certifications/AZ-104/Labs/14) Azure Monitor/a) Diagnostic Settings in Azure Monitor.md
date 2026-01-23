## Diagnostic settings in Azure Monitor

### Summary

This lab demonstrates how to configure diagnostic settings in Azure Monitor for a virtual machine in order to collect logs and metrics and stream them to a Log Analytics workspace. The lab includes creating a Log Analytics workspace, creating a virtual machine, and configuring the diagnostic settings in Azure Monitor for the virtual machine's Public IP address.

### Section 1: Create a Log Analytics workspace

-   1.1
    
    Log in to the Azure portal at [https://portal.azure.com/](https://portal.azure.com/).
    
    ✋
    
-   1.2
    
    In the Search Tab, search for "Log analytics". And Click on **Log Analytics workspace**
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+1.png)

-   1.3
    
    Enter a name for your workspace, choose your desired subscription and resource group.  
    
    ✋
    
-   1.4
    
    Select a location that is closest to your Azure resources. Then click Review and Create. Review your settings and click "Create" to create the workspace.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+2.png)

### Section 2: Create a resource

In this example, we'll use a **Virtual machine**. If you already have a resource (e.g. a virtual machine, a storage account, a web app, etc.), you won't need to create one.

-   1.5
    
    In the Search Tab, search for "Virtual machine". And Click on **Virtual machine**. You can also use the left-hand menu/blade.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+3.png)

-   1.6
    
    Click on Create. Then click on Azure Virtual Machine.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+4.png)

-   1.7
    
    Enter in the Settings and parameters.
    
    ✋
    
-   Create a new resource group: exampro-rg
-   Virtual machine name: exampro-vm
-   Image: Windows Server 2019 Datacenter - x64 Gen2
-   Size: Standard\_B1s, username: exampro1 and password: Testing123456
-   Select inbound ports: HTTP(80), SSH(22), RDP (3389)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+5.png)

-   1.8
    
    Click Review and Create. Review your settings and click "Create" to create the VM.
    
    ✋
    

### Section 3: Configure Diagnostic Settings

-   1.9
    
    In the Search Tab, Search for Monitor, and click on Monitor.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+6.png)

-   1.10
    
    On the left-hand menu, click on Diagnostic Settings.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+7.png)

-   1.11
    
    Here, there is a list of resources we can select to view the diagnostic settings. For the Virtual Machine we created, a network interface, network security group, and Public IP Address was already created for it. We can select any of the resources to view the diagnostic settings, but for this example, we'll select the Public IP address.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+8.png)

-   1.12
    
    After selecting the Public IP address, click on + Add diagnostic setting
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+9.png)

-   1.13
    
    Select the Logs and/or metrics you want to collect from the resource. And select the destination that you want to stream it to. In this case, we'll select all of logs and metrics: so audit, allLogs, and AllMetrics. For the destination detail, we'll select the Log Analytics workspace that we created earlier.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+10.png)

-   1.14
    
    After selecting the diagnostic settings, click on save.
    
    ✋
    
-   1.15
    
    Delete and Clean up resources
    
    ✋
    

### Reference

[Diagnostic settings in Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/diagnostic-settings?tabs=portal)