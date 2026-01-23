## Scaling Azure App Service

**Section 1 - Scaling Azure App Service**

-   1.1
    
    Search for scale in App Service, Scaling up (App Service plan) is upgrading to a bigger or better instance, no necessary in this demo.
    
    ✋
    
-   1.2
    
    Go to Scale-Out, Click on "Custom Autoscale", Instance Limits: Maximum: 2
    
    ✋
    
-   1.3
    
    Click on +Add a rule
    
    ✋
    
-   Time aggregation: Maximum
-   Metric threshold to trigger scale action: 10
-   Duration (in minutes): 5
-   Time grain statistic: Maximum

Click Add, Save

-   1.4
    
    Click on "Run History", Click on "1 Hour", Click "Save"
    
    ✋
    
-   1.5
    
    Adjusting the settings of the rule may be needed, may be difficult to trigger a scale-out. But you get the idea of scaling out when it hits specific criteria that you set.
    
    ✋
    
-   1.6
    
    Go to resource group voyager - delete resource group when you are finished.
    
    ✋
    

**Note**: Azure App Service does not automatically scale in (i.e., decrease the number of instances) without specific configuration. You need to define scaling rules or use auto-scaling settings to control when and how your App Service should scale in. You can configure **scale-in rules** for your Azure App Service using the Azure Portal, Azure CLI, Azure PowerShell, or ARM templates. These rules define the conditions under which your App Service should scale in. For example, you might specify that the service should scale in when CPU utilization drops below a certain threshold for a specified period.