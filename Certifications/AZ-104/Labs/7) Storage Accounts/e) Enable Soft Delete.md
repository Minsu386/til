## Enable and Manage Soft Delete for Containers

### Summary

This lab demonstrates how to enable and use **container soft delete** in an Azure Storage account. Soft delete protects against accidental or erroneous deletion by allowing you to recover containers (and their contents) within a specified retention period. You will:

1. Enable soft delete for containers in the Azure portal.
2. View containers that have been soft-deleted.
3. Restore a deleted container within the retention period.

---

### Section 1: Enable Soft Delete for Containers

- 1.1
    
    Log in to the Azure portal at [https://portal.azure.com/](https://portal.azure.com/).
    
- 1.2
    
    Navigate to your **Storage account**.
    
- 1.3
    
    In the left-hand menu, under **Data management**, click on **Data protection**.
    

![](https://exampro-support.s3.us-east-1.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Soft-delete/Soft-delete-1.png)

- 1.4
    
    Under **Recovery**, check **Enable soft delete for containers**.
    
- 1.5
    
    Specify a retention period (between **1–365 days**). Microsoft recommends at least **7 days**.
    
- 1.6
    
    Click **Save** to apply the changes.
    

### Section 2: View Soft-Deleted Containers

- 2.1
    
    In the same storage account, go to **Containers** in the left-hand menu.
    
- 2.2
    
    Use the **Show active and deleted containers** dropdown to include deleted containers in the list.
    

![](https://exampro-support.s3.us-east-1.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Soft-delete/Soft-delete-2.png)

- 2.3
    
    Confirm that containers with status **Deleted** appear in the list.
    

### Section 3: Restore a Soft-Deleted Container

- 3.1
    
    From the **Containers** view, select a container with the status **Deleted**.
    
- 3.2
    
    Open the **context menu (⋮)** for the container and click **Undelete**.
    

![](https://exampro-support.s3.us-east-1.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Soft-delete/Soft-delete-3.png)

- 3.3
    
    Verify that the container’s status changes to **Active** and it is restored successfully.
    

### Section 4: Clean Up

- 4.1
    
    If you no longer need soft delete enabled, return to **Data protection** and uncheck the option.
    
- 4.2
    
    To avoid charges, delete any test containers or storage accounts you created.
    

### Reference

- [Soft delete for containers](https://learn.microsoft.com/azure/storage/blobs/soft-delete-container-overview)
- [Enable and manage soft delete](https://learn.microsoft.com/azure/storage/blobs/soft-delete-container-enable)