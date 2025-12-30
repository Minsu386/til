## Create a File Share with Azure Files

### Reference

[Use Azure Files with Linux](https://docs.microsoft.com/en-us/azure/storage/files/storage-how-to-use-files-linux?tabs=smb311)

[Use an Azure file share with Windows](https://docs.microsoft.com/en-us/azure/storage/files/storage-how-to-use-files-windows)

[Quickstart: Create and manage Azure Files share with Windows virtual machines](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-quick-create-use-windows)

**Section 1 - Create storage account, virtual machine, and file share**

- 1.1
    
    Search for storage accounts, click +Create, Create a new storage account
    
- Create a new resource group: kivas
- Region: (US) East US (or any preferred region is fine)
- Storage account name: kivas (or any available name e.g. kivas1)
- Performance: Standard
- Redundancy: LRS or GRS is fine since it's only a test that will be deleted later.

Enter in other information, etc. Hit Review, and Create

- 1.2
    
    Search a Virtual Machine, +Create a virtual machine, select Linux, or whichever is preferred.
    
- Select resource group: kivas
- Virtual machine name: kivas (or any name you prefer)
- Location: Central US
- Availability Options: Availability Zone
- Availability Zone: 1
- Image: Ubuntu Server 20.04 LTS - Gen2, or any Ubuntu Server preferred
- Size: See all sizes: Standard_B1ls - 1vcpu, 0.5 GiB memory. (or the cheapest option)
- Username: azureuser, Password: Testing123456
- Select inbound ports: SSH (22)

Hit Review + Create

- 1.3
    
    Go back to the storage account "kivas". Click on **File Shares**
    
- 1.4
    
    Create a File Share. Name: kivas, Quota: 3 (This may not be needed), Select Tier: Transaction optimized.
    
- 1.5
    
    Go to **Networking** on your Virtual Machine **kivas**, add an **inbound port rule**
    
- Destination port range: 445
- Protocol: TCP
- 1.6
    
    Go back to **File Share** in storage account "kivas", click on the file share **kivas** created earlier, click **"Connect"**
    

**Section 2 - Networking**

- 2.1
    
    Go back to networking on Virtual machine "kivas", open up Cloud shell, make sure it's on bash. Go to **Overview** and copy the public IP address
    
- 2.2
    
    type in **ssh azureuser@****20.83.43.216 <- (paste the public IP address)**, press Yes, type in the password: Testing123456
    
- 2.3
    
    type in **sudo apt update && sudo apt install cifs-utils**
    
- 2.4
    
    From the File Share Overview - Connect, On the Linux tab, Copy the **Mount point command**
    
- **Example:** sudo mkdir /mnt/kivas if [ ! -d "/etc/smbcredentials" ]; then sudo mkdir /etc/smbcredentials fi if [ ! -f "/etc/smbcredentials/kivas1.cred" ]; then sudo bash -c 'echo "username=kivas1" >> /etc/smbcredentials/kivas1.cred' sudo bash -c 'echo "password=DstGSYPjPGntoLjKkP7uZRxeUecDAhdXzNgSPqYO+E6wQ8ltu2Yh64iqiHk87ozEs/+OIlT8wnL/8/bICOe/OA==" >> /etc/smbcredentials/kivas1.cred' fi sudo chmod 600 /etc/smbcredentials/kivas1.cred

sudo bash -c 'echo "//kivas1.file.core.windows.net/kivas /mnt/kivas cifs nofail,vers=3.0,credentials=/etc/smbcredentials/kivas1.cred,dir_mode=0777,file_mode=0777,serverino" >> /etc/fstab' sudo mount -t cifs //kivas1.file.core.windows.net/kivas /mnt/kivas -o vers=3.0,credentials=/etc/smbcredentials/kivas1.cred,dir_mode=0777,file_mode=0777,serverino

- 2.5
    
    Enter in the **Mount point command** in the Cloud Shell Bash, sudo command lines as shown in the video. Timestamp: 7:45~
    

**Section 3 - File Share**

- 3.1
    
    Go to file share, upload a file such as an image.
    
    ✋
    
- 3.2
    
    Go to bash, run ls. You can try out some command lines such as
    
- **mkdir themosttoys** to make a new directory named themosttoys
- **mv kivas_fajo.jpg themosttoys** to move kivas_fajo.jpg to the directory **themosttoys**
- 3.3
    
    This should show your file. Files are located in your file share, refresh to update. After finished, delete your resource group "kivas"