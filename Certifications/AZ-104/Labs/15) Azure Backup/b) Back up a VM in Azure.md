## Back up a virtual machine in Azure

### Summary

This lab demonstrates how to back up a virtual machine in Azure. The lab includes creating a virtual machine, creating a Recovery Services vault, configuring backup for the virtual machine, and creating a custom policy. The custom policy includes settings such as frequency, retention of daily, weekly, monthly, and yearly backup points.

### Section 1: Create a VM

In this example, we'll use a **Virtual machine**. If you already have a resource (e.g. a virtual machine, a storage account, a web app, etc.), you won't need to create one.

-   1.1
    
    In the Search Tab, search for "Virtual machine". And Click on **Virtual machine**. You can also use the left-hand menu/blade.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+3.png)

-   1.2
    
    Click on Create. Then click on Azure Virtual Machine.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+4.png)

-   1.3
    
    Enter in the Settings and parameters.
    
    ✋
    
-   Create a new resource group: exampro-rg
-   Virtual machine name: exampro-vm
-   Image: Windows Server 2019 Datacenter - x64 Gen2
-   Size: Standard\_B1s, username: exampro1 and password: Testing123456
-   Select inbound ports: HTTP(80), SSH(22), RDP (3389)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Diagnostic+Settings+using+Azure+Monitor/Diagnostic+Settings+using+Azure+Monitor+-+5.png)

-   1.4
    
    Click Review and Create. Review your settings and click "Create" to create the VM.
    
    ✋
    

### Section 2: Create a Recovery Services vault

-   2.1
    
    On the Search Tab, search for "Recovery Services vaults".
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+1.png)

-   2.2
    
    Click on "Create" to create a new Recovery Services vault.
    
    ✋
    
-   2.3
    
    Fill out the required fields, such as the subscription, resource group, and vault name. Choose a region close to the location of your virtual machine for optimal performance.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+2.png)

-   2.4
    
    Click on "Review + create" and then "Create" to create the Recovery Services vault.
    
    ✋
    

### Section 3: Configure backup for the virtual machine

-   3.1
    
    On the search tab, search for virtual machines, or resource group. Select the virtual machine that you want to back up. In this example, it's **exampro-vm**
    
    ✋
    
-   3.2
    
    In the virtual machine blade, click on "Backup" in the left-hand menu.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+3.png)

-   3.3
    
    After clicking the Backup blade. You will need to select the settings for the Azure Backup for Azure VMs.
    
    ✋
    
-   Vault: exampro-rsvault
-   Policy sub type: Standard
-   Choose backup policy: You can choose DefaultPolicy. But for this setting, we'll make things more interesting, so we'll create a custom policy.

### Section 4: Create a custom policy

-   4.1
    
    Click on "Create a new policy".
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+4.png)

-   4.2
    
    Provide the new policy a name. Enter the preferred backup schedule settings. You can customize the policy however you like, but we'll go with the ones listed in below or in the screenshot.
    
    ✋
    
-   Policy name: MyCustomPolicy
-   Frequency: Daily | Time: 10:00 AM | Timezone: (UTC-5:00) Eastern Time (US & Canada)
-   Instant Restore: 2 Days(s)
-   Retention of daily backup point: 90 day(s)
-   Retention of weekly backup point: On Sunday At 10:00 AM for 12 Week(s)
-   Retention of monthly backup point: Week Based | On First | Day Sunday | At 10:00 AM | for 60 Months(s)
-   Retention of yearly backup point: Week Based | January | On First | Day Sunday | At 10:00 AM | For 60 Months(s)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+5.png)

-   4.3
    
    Click on "OK" to continue.
    
    ✋
    
-   4.4
    
    Select the new policy created "MyCustomPolicy". And click on Enable Backup.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+6.png)

### Section 5: Monitor backup progress

-   5.1
    
    Navigate to the VM created. E.g. exampro-vm. Click on the **Backup** blade.
    
    ✋
    
-   5.2
    
    Click on Backup Now. Note: This does take a while to complete. So this step can be skipped.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+7.png)

-   5.3
    
    Select the retain backup till: 06/07/2023. As of creating the follow-along. This will be different for you, or set the date to what you prefer. Then Click on **"OK"**
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+8.png)

-   5.4
    
    Navigate to the Recovery Service Vault: exampro-rsvault
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+9.png)

-   5.5
    
    Click on the "Backup Jobs" blade.
    
    ✋
    
-   5.6
    
    Here you can monitor all the Backup Jobs you've set up. You can see the status of the exampro-vm back up was completed. As well as the backup operation.
    
    ✋
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Back+up+a+virtual+machine+in+Azure/Back+up+a+virtual+machine+in+Azure+-+10.png)

-   5.7
    
    After that, you can delete and clean the resources to prevent any charges.
    
    ✋
    

### Reference

[Back up a virtual machine in Azure](https://learn.microsoft.com/en-us/azure/backup/quick-backup-vm-portal)