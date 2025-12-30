## Setting up Public Load Balancers for VMs

### Summary

This lab demonstrates skills in creating and configuring virtual networks, virtual machines, and public load balancers using the Azure portal. Users will learn how to create and deploy virtual machines, configure virtual networks and load balancers, and configure backend pools, health probes, and load balancing rules. These skills are essential for deploying and managing applications and services in Azure and ensuring high availability and scalability.

### Section 1: Create a Virtual Network

- 1.1
    
    On the Search Tab, search for Virtual Networks, and click on Virtual Networks.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+1.png)

- 1.2
    
    Click on + Create to create a Virtual Network. Provide the resource group, resource name, and region. We can use the default settings for IP addresses and subnets.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+2.png)

- 1.3
    
    Click on Review + Create, then click Create.
    

### Section 2: Create two VMs

- 2.1
    
    In the Search Tab, search for "Virtual machine". And Click on **Virtual machine**. You can also use the left-hand menu/blade.
    
- 2.2
    
    Click on Create. Then click on Azure Virtual Machine.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+3.png)

- 2.3
    
    Enter in the Settings and parameters.
    
- Create a new resource group: exampro-rg
- Virtual machine name: **exampro-vm**
- Image: Windows Server 2019 Datacenter - x64 Gen2
- Size: `Standard_B1s | or Standard_B2s`
- username: exampro | password: Testing123456
- Select inbound ports: HTTP (80), HTTPS(443), SSH (22), RDP (3389)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+4.png)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+5.png)

- 2.4
    
    Click on Networking. Ensure that your VM in placed in the **exampro-vnet** that you created in **Section 1**. You can leave the default subnet settings. And the Public IP can remain default.
    
- NIC networking settings: Basic
- Public inbound ports: Allowed selected ports

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+6.png)

- 2.5
    
    Click Review and Create. Review your settings and click "Create" to create the VM.
    
- 2.6
    
    Repeat the same steps to create the second VM. Ensure it is also placed in the virtual network: **exampro-vnet**. You can name it **exampro-vm2**
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+7.png)

### Section 3: Configuring the two VMs

- 3.1
    
    On the click on the first virtual machine. exampro-vm1. Click on the "Connect" blade. then Click on Download RDP File.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+8.png)

- 3.2
    
    Save the RDP File. Double click on exampro-vm1 RDP File and click on Connect.
    
- 3.3
    
    Enter in the username: exampro and password: Testing123456
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+8.1.png)

- 3.4
    
    Click on the "Local Server" tab. Click on IE Enhanced Security Configuration: On. Select "Off" for both Administrators and Users. Then click on "OK"
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+9.png)

- 3.5
    
    Click on the "Dashboard" tab. And click on "Add role and features"
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+10.png)

- 3.6
    
    Click "Next" for all the steps until you reach "Server Roles". On the Server Roles tab, click on Webserver (IIS). This is to allow you to create a web server on the virtual machine.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+11.png)

- 3.7
    
    Click on "Add Features"
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+12.png)

- 3.8
    
    Click on Next for the Server Roles, Features, Web Server Role (IIS), and Role Services. When you reach the Confirmation tab, click on "Install". You'll need to install this on the second VM as well.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+13.png)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+14.png)

- 3.9
    
    After the installation is complete. On the top right. Click on "Tools". Click on Internet Information Services (IIS) Manager.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+15.png)

- 3.10
    
    Click to expand exampro-vm1, and expand Sites. then Right Click on Default Web Site and click on "Explore".
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+16.png)

- 3.11
    
    Open the iisstart.png file.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+17.png)

- 3.12
    
    This is how the website will appear when you use the Public IP. But, we want to make the two VMs look different. So we'll add a text for **Exampro-vm1**. Remember to save the change.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+18.png)

- 3.13
    
    Repeat all the steps: exampro-vm2 > Connect using RDP file > install IIS > edit the iisstart.png for the second VM - **exampro-vm2**.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+19.png)

- 3.14
    
    To test that the web server is working for VM1, you can navigate to **exampro-vm1**. Copy the **Public IP address**. Paste that address on the webpage. and the webpage for **exampro-vm1** should appear. You can do the same for exampro-vm2 to confirm. The preparation for the two VMs is now complete.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+20.png)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+21.png)

### Section 4: Create and Configure Load Balancer

- 4.1
    
    On the Search Tab, search for Load Balancers. Click on Load Balancers.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+22.png)

- 4.2
    
    Click the Add button to create a new load balancer.
    
- 4.3
    
    Fill in the basic information for the load balancer such as the name and region. Ensure to choose **Public** as the load balancer type. Choose the standard SKU.
    
- Name: MyLB
- Region: EastUS
- SKU: Standard
- Type: **Public**
- Tier: Regional

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+23.png)

- 4.4
    
    Click on the next section called "Frontend IP configuration". Click on Add a Frontend IP configuration.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+24.png)

- 4.5
    
    Provide the name, frontend IP address, backend pool, and the necessary information required.
    
- Name: MyLB
- IP version: IPv4
- IP type: IP address
- Public IP address. Click on **Create new**. Name: MyPublicIP.

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+25.png)

- 4.6
    
    Click "OK", then click on "Add"
    

### Section 5: Create and Configure Backend pools, inbound rules, and health probe.

- 5.1
    
    Click on the next tab "Backend pools". Click on + Add a backend pool.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+26.png)

- 5.2
    
    Provide the name, Vnet, and Backend Pool config.
    
    ✋
    
- Name: MyBackendpool
- Virtual network: exampro-vnet (exampro-rg)
- Backend Pool Configuration: NIC

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+27.png)

- 5.3
    
    On **IP Configurations to backend pool**, click on "+ Add". Select the two VMs you created earlier: **exampro-vm1** and **exampro-vm2**. Click on Add and Click on Save.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+28.png)

- 5.4
    
    Click on the next tab called "Inbound rules"
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+29.png)

- 5.5
    
    Click on +Add a load balancing rule
    
- 5.6
    
    Provide the name, frontend IP address, backend pool, and information required.
    
- Name: MyLBrule
- Frontend IP address: MyFrontendIP (To be created)
- Backendpool: MyBackendpool
- Protocol: TCP
- Port: 80
- Backend port: 80
- Session persistence: None
- Idle timeout (min): 4
- TCP reset: Disabled
- Floating IP: Disabled

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+30.png)

- 5.8
    
    We will also create a **Health Probe**, so Click on **Create new**
    
- 5.9
    
    Give the health probe a name and configure the probe settings such as the protocol, port, and interval.
    
- Name: MyHP
- Protocol: TCP
- Port: 80
- Interval: 5

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+31.png)

- 5.10
    
    Click on OK. then Click on "Add"
    
- 5.11
    
    Skip Outbound rules and tags. Click on Review + Create. And Create.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+32.png)

### Section 6: Verify and monitor the Load Balancer and VMs.

- 6.1
    
    Navigate to the Load Balancer. Click on the **Insights** blade
    
- 6.2
    
    If you see the topology is similar to the image below, and both VMs are connected then it's successful. (This can take a while to generate, and refresh if needed)
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+34.png)

- 6.3
    
    Click on Frontend IP configuration, copy the load balancer IP address. paste it onto a webpage.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+35.png)

- 6.4
    
    To verify that it works. If you see "exampro-vm1" on the LB IP address web server page. Navigate to the "exampro-vm1" and click on "STOP" to turn it off. if you see exampro-vm2, turn off exampro-vm2.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+36.png)

- 6.5
    
    After the VM has stopped, it may take a while for the webpage to change over to the second VM that is still running.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+37.png)

- 6.6
    
    Confirm at the Load Balancer Insights that only one VM should be running on with the load balancer IP connected to the web server.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Setting+up+Public+LBs+for+VMs/Setting+up+Public+LBs+for+VMs+-+38.png)

- 6.7
    
    After this is confirmed and complete, you may delete and clean up the resources created in this lab.