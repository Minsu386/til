## Attaching, Partitioning and Mounting a Disk

**Section 1 - Partition and Mount a Disk using Linux Virtual Machine**

- 1.1
    
    Search for Virtual machine, +Create Virtual Machine
    
    ✋
    
- Create a new resource group: dax
- Virtual machine name: dax
- Region: (US) East US
- Availability options: Availability zone or No redundancy required since you will deleting it up after testing anyways
- Availability zone: 1
- Image: Ubuntu Server 20.04 LTS - Gen1
- Size: Standard_B1ls - 1 vcpu, 0.5 GiB memory
- Authentication type: Password, Username: azureuser, Password: Testing123456

Hit Review and Create

- 1.2
    
    Go to your virtual machine "dax", Go to disks, Click on +Create and attach a new disk, Name: mySecondDisk, Storage Type: Standard SSD, Click Save
    
    ✋
    
- 1.3
    
    Go to your virtual machine "dax", Copy your Public IP address, e.g. 104.211.26.53, Click on Cloud Shell, Enter in **ssh [azureuser@104.211.26.53](mailto:azureuser@104.211.26.53)**, type yes, and your password: Testing123456
    
    ✋
    
- 1.4
    
    **man parted** to view instructions, press q to quit, type in **man mount**, press q to quit, type in **sudo parted /dev/sdc --script mklabel gpt mkpart xfspart xfs 0% 100%**, hit Enter
    
    ✋
    
- 1.5
    
    type in **sudo mkfs.xfs /dev/sdc1**, hit Enter, type in **sudo partprobe /dev/sdc1**, type in **man mkfs**, press q
    
    ✋
    
- 1.6
    
    type in sudo mkdir /dax && sudo mount /dev/sdc1 /dax
    
    ✋
    
- 1.7
    
    df -h | grep -i "sd", enter in cd /dax/, enter in sudo touch hello.txt
    
    ✋
    
- 1.8
    
    Back one directory **cd ..**, Enter in **sudo -i blkid**, copy **/dev/sdc1: UUID="43d246b8-be1f-4032-b2a4-ff66a1457eef" TYPE="xfs" PARTLABEL="xfspart" PARTUUID="71651c49-cb69-42e2-9beb-63201ec8ec0a"** - copy the sdc1
    
    ✋
    
- 1.9
    
    sudo vi /etc/fstab
    
    ✋
    
- 1.10
    
    UUID=43d246b8-be1f-4032-b2a4-ff66a1457eef /dax xfs defaults,nofail 1 2, Press ESC, Press :, Enter in wq
    
    ✋
    

**Section 2 - Disks, Disks with Windows Virtual Machine**

- 2.1
    
    Go to mySecondDisk, Click Create a SnapShot, Name: mydiskbackup, Storage type: Standard HDD
    
    ✋
    
- 2.2
    
    Go to virtual machines, Create a new Virtual machine with a Windows image
    
    ✋
    
- Use the same resource group: dax
- Virtual machine name: daxwindows
- Region: (US) East US
- Availability options: Availability zone
- Availability zone: 1
- Image: **Windows Server 2019 Datacenter - Gen2**
- Size: Standard_D2s_v3 - 2 vcpus, 8 GiB memory
- Authentication type: Password, Username: dax, Password: Testing123456

Hit Review and Create.

- 2.3
    
    Go to your virtual machine "daxwindows", Go to disks, Click on +Create and attach a new disk, Name: myWindowsDisk, Storage Type: Premium SSD, Click Save
    
    ✋
    
- 2.4
    
    Go to daxwindows virtual machine, go to Connect, Download RDP File, Run the file and enter in Username: azureuser and password: Testing123456
    
    ✋
    
- 2.5
    
    Open up PowerShell, type in **Get-Disk | Where partitionstyle -eq "raw" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "myNewDisk" -Confirm: $false**
    
    ✋
    

![](https://images2.imgbox.com/90/8b/lNc6QXMK_o.png)

- 2.6
    
    **Alternative way** to format disks, Go to File Explorer, Local C: Drive, Format Drive, File system: NTFS (Default), Click Start
    
    ✋
    
- 2.7
    
    **Alternative way**: search for disks on the search tab, Go to "Create and format hard disk partitions", **Disk Management**
    
    ✋
    

![](https://images2.imgbox.com/88/82/261nerjm_o.png)

- 2.8
    
    After completing the partioning the mounting, go to resource groups "dax" and delete.