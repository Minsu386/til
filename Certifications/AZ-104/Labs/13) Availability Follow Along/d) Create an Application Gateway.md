## Create an Application Gateway

**Section 1 - Create an Application Gateway**

-   1.1
    
    Search for Application Gateways, and Click on +Create
    
    ✋
    
-   Resource group: wolf
-   Application gateway name: wolfagw
-   Region: Central US (Some regions don't support Availability zone)
-   Enable autoscaling: No
-   Instance count: 1
-   Availability zone: Zone 1, 2, 3
-   Virtual network: wolfvnet499 (Check your Virtual machine scale sets - wolfscaleset - to check your Vnet
-   Go to Subnet wolfvnet499, **Address space**: 10.0.2.0/24

Click Save

-   1.2
    
    Go to **Subnets**, Click +Subnet
    
    ✋
    
-   Name: **vgw**, Hit Save
-   1.3
    
    Go back to Create application gateway, Subnet: vgw (10.0.2.0/24)
    
    ✋
    
-   Go to FrontEnds Tab, Public IP Address: Create new: wolfvgw
-   Add a backend pool, Name: backend, Target Type: VMSS, Target: wolfscaleset, Click Add
-   1.4
    
    Go to Configuration, Click on Add a routing rule
    
    ✋
    
-   Rule name: myrules
-   Listener name: mylistener
-   Frontend IP: Public
-   Backend targets: backend target: backend
-   Add new HTTP settings, HTTP settings name: myhttpsettings, Click Add

Hit Review and Create

**Section 2 - wolfscaleset**

-   2.1
    
    Click on wolfscaleset, click on Instances, check all three: wolfscaleset_1, wolfscaleset_3, and wolfscaleset\_4.
    
    ✋
    
-   2.2
    
    Go to wolfagw application gateway, go to overview, copy the Public IP Address: e.g. 52.255.138.58 (remove the wolfvgw), and the server should be functional!
    
    ✋
    
-   2.3
    
    Once you are finished, Click on resource group "wolf" and delete.
    
    ✋