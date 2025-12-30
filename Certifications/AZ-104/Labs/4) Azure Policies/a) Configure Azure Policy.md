## Configure Azure Policy

### Section 1: Configure Azure Policy

- 1.1
    
    In your web browser visit: [https://portal.azure.com/#home](https://portal.azure.com/#home)
    
- 1.2
    
    In the Search Tab, look for Policy
    
- 1.3
    
    Click on the default policy assigned
    
    ✋
    

![](https://images2.imgbox.com/cb/fb/XegKP1mh_o.png)

- 1.4
    
    Click on Assignments
    
- 1.5
    
    Click on ASC Default (**You can skip this step if there is no "ASC Default" in your policy service, it's just a pre-set or an example that Andrew goes through to show what it's like**)
    

![](https://images2.imgbox.com/cf/8d/AU3LPDAR_o.png)

- 1.6
    
    This is the default assignment assigned to you. You can configure many settings such as Basics, Parameters, Remediation, etc as you see fit. Then Review and Save. (**Can skip if there's no "ASC Default"**)
    

![](https://images2.imgbox.com/f5/d9/ZmOlhvVU_o.png)

- 1.7
    
    Click on Definitions
    
- 1.8
    
    Click on Category, Search for the category desired (In this demo: **Compute**)
    
- 1.9
    
    Click on **Audit virtual machines without disaster recovery configured** used in this demo
    

![](https://images2.imgbox.com/f2/bd/n6S9uIEj_o.png)

- 1.10
    
    Click on Assign
    

![](https://images2.imgbox.com/a4/30/uh0P2soj_o.png)

- 1.11
    
    Click on Scope
    
- 1.12
    
    Assign the Resource Group to the Virtual machine created earlier (bajor_group) used in the demo (You can create your own virtual machine to try it out too)
    
- 1.13
    
    Click on Select, then Review the parameters, Remediations, and other settings to your liking
    
- 1.14
    
    Click on Review + Create
    

![](https://images2.imgbox.com/8b/36/YdNsdd1u_o.png)

- 1.15
    
    Click on Overview
    
- 1.16
    
    After a short wait, the new policy compliance created should appear on your list of policies
    

![](https://images2.imgbox.com/c3/b3/1I8aesU5_o.png)

### Reference

[Quickstart: Create a policy assignment to identify non-compliant resources](https://docs.microsoft.com/en-us/azure/governance/policy/assign-policy-portal)