## Create a DNS Zone and Record Set

-   1.1
    
    Search for **Virtual Machines** in the search tab, Click on +Create to create a Virtual machine
    
    ✋
    

Enter in the information

-   Create a new Resource Group: worf
-   Virtual machine name: worf (or whichever is available)
-   Region: Central US
-   Image: Ubuntu Server 20.04 LTS - Gen1
-   Size: Standard\_B2s - 2vcpus, 4 GiB memory
-   Username: azureuser, Password: Testing123456
-   Advanced Custom: #!/usr/sh sudo apt install apache2 -y

Click Review+Create

-   1.2
    
    Search for "DNS", click on DNS zones, Click +Create. Name: worf.com, Review and Create
    
    ✋
    
-   1.3
    
    Click on +Record Set, Name: google, Type: CNAME - Link your subdomain to another record, Alias: google.com
    
    ✋
    
-   1.4
    
    Click on +Record Set, Name: site, Type: A - Alias record to iPv4 address, use the IP address from the Virtual Machine **worf**
    
    ✋
    
-   1.5
    
    Click on +Record Set, Name: site2, Type: A, Alias: Azure resource, Azure resource: worf-ip
    
    ✋
    
-   1.6
    
    Click on +Child Zone, name: app, Create
    
    ✋
    
-   1.7
    
    After exploring the DNS Zone, delete the resource group **worf**
    
    ✋