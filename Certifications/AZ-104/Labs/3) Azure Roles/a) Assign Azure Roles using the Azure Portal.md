## Assign Azure roles using the Azure portal

### Summary

This lab demonstrates how to assign roles in Azure using the Azure portal. It provides hands-on experience in creating, modifying, and deleting role assignments, as well as how to use the Access control (IAM) blade in the Azure portal to manage access to Azure resources.

### Section 1: Identify the needed scope | Create a resource group

- 1.1
    
    In your web browser visit: [https://portal.azure.com/#home](https://portal.azure.com/#home)
    
- 1.2
    
    In the Search Tab, search for **resource group**.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+1.png)

We need to identify the scope, we can use Management groups, Subscriptions, Resource groups, or a specific resource. In this example, we'll use resource groups, so we'll need to create one unless you already have one available to use.

- 1.3
    
    Click on **Create**. Select the subscription. Enter the name of the resource group. Select the Region.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+2.png)

- 1.4
    
    Skip the tags, then click on **Review and Create**.
    

### Section 2: Open the Add role assignment page

- 1.5
    
    Click **Access control (IAM)**. Click the Role Assignments tab to view the role assignments at this scope. Click **Add**. On the drop-down menu, click **Add role assignment**.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+3.png)

### Section 3: Select the desired role, member(s), and assign the role

- 1.6
    
    Select Job Functions
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+4.png)

- 1.7
    
    On the Role Tab, you have a wide selection of Roles you can assign. For this example, we will choose the Reader Role.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+5.png)

- 1.8
    
    On the Members Tab, we'll need to select the Members, Groups, or service principal that we want to assign to the Role. So Click on Select Member(s).
    
- 1.9
    
    Select the Member(s) you want to Assign the Reader Role. In this example, we'll select "Chris Green". (If you don't have any members, you can simply create users in Azure AD)
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+6.png)

- 1.10
    
    After reviewing the information entered, Click on Review and Assign.
    

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+7.png)

![](https://exampro-support.s3.amazonaws.com/Microsoft+Azure/AZ-104/AZ-104+Follow+Alongs/Assign+Azure+roles+using+the+Azure+portal/Assign+Azure+roles+using+the+Azure+portal+8.png)

- 1.11
    
    You have successfully assigned an Azure role using the Azure portal. Remember that the assigned role will be granted the associated permissions for the specified resource(s). If you need to modify or revoke a role assignment, you can do so from the IAM page.
    

### Reference

[Assign Azure roles using the Azure portal](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal)