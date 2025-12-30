## Moving Resources

### Section 1: Create a Resource group

- 1.1
    
    In your web browser visit: [https://portal.azure.com/#home](https://portal.azure.com/#home)
    
- 1.2
    
    In the Search Tab, look for Resource Groups
    
- 1.3
    
    Click on Resource groups
    

![](https://images2.imgbox.com/91/55/JZjkx5Fa_o.png)

- 1.4
    
    Click on Add, enter the subscription, name of the resource group, and select the region you want
    
- 1.5
    
    Click on Review + Create
    

![](https://images2.imgbox.com/ee/7b/VDpGDlcr_o.png)

You should now have created two resource groups named: (Shown in demo)

- the-federation-of-planets located in East US
- the-klingon-empire located in West US

### Section 2: Create a Disk

- 2.1
    
    Search for Disks in the Search Tab
    
- 2.2
    
    Click on Disks
    

![](https://images2.imgbox.com/3a/7c/tIhysaum_o.png)

- 2.3
    
    Click on Add, Enter in the Subscription and resource group: **the-federation-of-planets**
    
- 2.4
    
    Enter in the Disk name (In this demo: **Dilithium**) , region, etc.
    
- 2.5
    
    Select a size for the Disk, Click on Review + Create
    

![](https://images2.imgbox.com/77/9a/Hy4VavjJ_o.png)

### Section 3: Moving Resources

- 3.1
    
    Click on the-federation-of-planets, Click on Overview, Click on Dilithium
    
- 3.2
    
    Click on Move to another resource group
    

![](https://images2.imgbox.com/0d/0a/C6xh13Yb_o.png)

- 3.3
    
    Click on the resource Dilithium
    
- 3.4
    
    Select Move these resources: **the-klingon-empire** (The second resource group created), Click OK
    

![](https://images2.imgbox.com/d4/99/38gfjeCV_o.png)

- 3.5
    
    Click on the-klingon-empire, Click on Overview
    
- 3.6
    
    You should now see the Dilithium Disk moved over from **the-federation-of-planets** to **the-klingon-empire**
    

![](https://images2.imgbox.com/75/c7/65g6Rmam_o.png)

### Section 4: Locks

- 4.1
    
    Click on the-klingon-empire, Click on Locks
    
- 4.2
    
    Click Add, Enter in select the lock type: Read-only or CanNotDelete, Click OK
    

![](https://images2.imgbox.com/d2/46/KirnI7Md_o.png)

For more details and rules on Locks refer to [Move resources to a new resource group or subscription](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/move-resource-group-and-subscription)

**Note**:

- If a read-only lock is applied to the resource group (source or destination), Azure will not permit moving resources into or out of that group.
- If only the individual resource itself has a read-only lock—and the resource group is unlocked—you can still move that resource successfully.

### Section 5: Delete Resource groups

- 5.1
    
    Click on the-federation-of-planets, Click on Overview
    
- 5.2
    
    Click on the Disk AntiMatter (shown in the demo), enter the resource group name, and confirm
    
- 5.3
    
    Click Delete
    

![](https://images2.imgbox.com/7d/d8/ebE954fr_o.png)

### Reference

- [Move resources to a new resource group or subscription](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/move-resource-group-and-subscription)
- [Understand resource locking in Azure Blueprints](https://learn.microsoft.com/en-us/azure/governance/blueprints/concepts/resource-locking)