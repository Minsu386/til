## Create a Linux VM and SSH

**Section 1 - Create Linux VM and SSH**

- 1.1
    
    Search for Virtual Machines, click on +Add Virtual Machine
    
    ✋
    

Settings

- Create a new resource group: Bajor
- Virtual machine name: Bajor
- Region: US East
- Availability zone: 1
- Image: Ubuntu Server 10.04 LTS - Gen1
- Size: Standard_B1ls
- Authentication type: SSH public key
- Username: bajor
- Generate new key pair
- Key pair name: bajor
    
- Select inbound ports: SSH(22), HTTP(80)
    

Disks

- OS disk type: Standard HDD
- Encryption: Default

Everything else in default is fine, Hit create, and download private key and create resource

- 1.2
    
    At the Bajor Virtual Machine resource, Click on Connect, click on the BASTION, Use Bastion
    
    ✋
    
- 1.3
    
    Search for Subnets, click on Address space, Add an additional address range: 10.0.2.0/24
    
    ✋
    
- 1.4
    
    Go back to Subnets, click on Bajor-vnet, click on Subnets, Click on + Subnet, Name: AzureBastionSubnet, Subnet address: 10.0.2.0/27
    
    ✋
    
- 1.5
    
    Connect using Azure Bastion, Enter in Username: bajor, check "SSH Private Key from Local File", Local File: bajor.pem
    
    ✋
    

**Section 2 - Ubuntu**

- 2.1
    
    You should be on Ubuntu 18.04.5 server, Enter in **sudo apt-get install apache2**, hit Y to continue, wait for it to install
    
    ✋
    
- 2.2
    
    Enter in cd /var/www/html/, ls, ps aux | grep httpd, ps aux | grep apache
    
    ✋
    
- 2.3
    
    Search for virtual machine, click on Bajor, copy the Public IP address, and test the IP address on webpage
    
    ✋
    
- 2.4
    
    Go to all resources, click on the bajor resource group and delete the resource group.
    
    ✋
    

### Reference

[Connect using SSH to a Linux virtual machine using Azure Bastion](https://docs.microsoft.com/en-us/azure/bastion/bastion-connect-vm-ssh)