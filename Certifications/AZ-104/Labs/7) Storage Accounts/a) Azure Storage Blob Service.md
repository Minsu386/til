## Azure Storage Blob Service

### Summary

Objective: To learn how to create a storage account, upload files, configure access levels, create snapshots, and restore snapshots in Azure. The tutorial provides a step-by-step guide for achieving this objective, including creating a storage account, uploading a file to a container, changing the access level of the blob, creating a snapshot, editing the snapshot, and restoring the snapshot.

Skills:

- Creating a storage account in Azure
- Uploading a file to a container in Azure
- Configuring the access level of the blob in Azure
- Creating a snapshot of the blob in Azure
- Restoring a snapshot in Azure

### Section 1: Create a Storage Account

- 1.1
    
    On the Search Tab, search for Storage Account, and click on Storage Accounts.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+1.png)

- 1.2
    
    Click on + Create to create a Storage Account.
    
- 1.3
    
    Provide the resource group, Storage account name, and region. We can select the performance as Standard. The redundancy is Geo-redundant storage (GRS).
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+2.png)

- 1.4
    
    Click on Review + Create, then click Create.
    
- 1.5
    
    Click on the Container blade. Click on + Create Container.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+3.png)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+4.png)

- 1.6
    
    Provide a name, and click on Create.
    

### Section 2: Upload a file to Container

- 2.1
    
    Click on Upload.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+5.png)

- 2.2
    
    Click on Browse for files. Click on the file you want to upload, or you can make a quick text file and write a short text like "SampleText". Click "Upload" to upload the file.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+6.png)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+7.png)

### Section 3: Configure the Access level of the blob

- 3.1
    
    Select the text file. Copy the URL of the sampletext.txt file.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+8.png)

- 3.2
    
    You should not have access to the file, so the file contents should not appear.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+9.png)

- 3.3
    
    Change the access level to "Blob (anonymous read access for blobs only). Container also works too.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+10.png)

- 3.4
    
    You should now be able to see the sample text once you use the URL.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+11.png)

### Section 4: Create a snapshot of the blob

- 4.1
    
    Select the "sampletext.txt" file. Click on "Create snapshot".
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+12.png)

- 4.2
    
    Click on the "Edit" tab. Change the text. Edit it to make sure it's different from the original. E.g. "SampleText Version 2. This is Version 2 of the SampleText"
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+13.png)

- 4.3
    
    Select sampletext.txt. Click on View Snapshots.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+14.png)

- 4.4
    
    Select "Promote". This will restore the snapshot that you saved earlier.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+15.png)

- 4.5
    
    The sampletext content should be restored to the snapshot before the edit.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Azure+Storage+Blob+Service/Azure+Storage+Blob+Service+-+16.png)

- 4.6
    
    Delete and clean up resources.