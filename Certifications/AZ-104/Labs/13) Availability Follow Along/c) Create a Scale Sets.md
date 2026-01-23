## Create a Scale Sets

**Section 1 - Create a Scale Sets**

-   1.1
    
    Go to shared image gallery, go to MyDef, go to 0.0.1, +Create a Virtual Machine Scale Set (VMSS)
    
    ✋
    
-   Resource group: wolf
-   Virtual machine scale set name: wolfscaleset
-   Availability zone: Zones 3
-   Username: azureuser and password: Testing123456
-   Initial instance count: 1

Click Review and Create

-   1.2
    
    Go to the Virtual machine scale sets, Click on wolfscaleset
    
    ✋
    
-   1.3
    
    Click Manual Autoscale, Instance count: 3, Click Save
    
    ✋
    
-   1.4
    
    Click on Health and repair, Enable application health monitoring: **Enabled_&, Enable automatic repairs: \*_Off**, Save
    
    ✋
    
-   1.5
    
    Click on **Upgrade policy**, **Upgrade mode**: Automatic - Instances will start upgrading immediately in random order, Save