## Backup VM using Images

**Section 1 - Backup VM using Images**

-   1.1
    
    Search for Virtual Machine, +Create Virtual Machine
    
    ✋
    
-   Create a new resource group: wolf
-   Virtual machine name: wolf
-   Image: Ubuntu Server 20.04 LTS - Gen1
-   Size: Standard\_B1s, username: azureuser and password: Testing123456
-   Select inbound ports: HTTP(80), SSH(22)
-   Advanced: Custom data: #!/bin/sh sudo apt install apache2 -y

Click Review and Create

-   1.2
    
    Go to the virtual machine: wolf, Copy the Public IP Address, test it to ensure apache is working.
    
    ✋
    
-   1.3
    
    Click on **Capture**, click No, capture only a managed image, Zone resiliency: Check, Hit Review and Create
    
    ✋
    
-   1.4
    
    Search for images, Click on Images, click on the wolf-image-20210817001807, Click on +Create VM
    
    ✋
    
-   1.5
    
    Go back to virtual machine, click on **Capture**, Automatically delete this virtual machine after creating the image: Enable, Yes, share it to a gallery as an image version, create new Target image gallery: **myGallery**, Target Image definition: **MyDef**, Version number: **0.0.1**
    
    ✋
    

Click Review and Create

-   1.6
    
    Search for **shared image gallery**, Click on MyDef, Click on 0.0.1
    
    ✋
    
-   1.7
    
    Delete VM wolf
    
    ✋
    

### Reference

[Back up an Azure VM from the VM settings](https://docs.microsoft.com/en-us/azure/backup/backup-azure-vms-first-look-arm)