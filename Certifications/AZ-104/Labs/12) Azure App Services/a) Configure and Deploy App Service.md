## Configure and Deploy App Service

**Section 1 - Configure and Deploy App Service**

-   1.1
    
    Go to your subscription, Go to **Resource providers**, Search "web" for **Microsoft.Web** and make sure it is registered if it's not.
    
    ✋
    
-   1.2
    
    Search for **App Services** in the search tab, Click on `+Create` to create a Web application, enter in the information
    
    ✋
    
-   Resource Group: voyager
-   Name: voyager-delta-flyer (or whichever is available)
-   Publish: Code
-   Runtime stack: Python 3.8
-   Operating System: Windows or Linux, whichever you prefer
-   Region: Canada East
-   Sku and size: Dev/Test: B1 100 total ACU | 1.75 GB memory | A-Series compute equivalent, Production: P1V2: 210 total ACU|3.5GB memory|Dv2-Series compute equivalent, click Apply

**Note**: If you do not see the "SKU and Size" section, it may now be located under the **Pricing Tier** or **Scale up (App Service plan)** sections in the left-hand menu of the App Service Plan configuration page.

Click Review and Create

-   1.3
    
    Go to your resource "voyager-delta-flyer" App Service, Click on **Deployment Center**, Click on Settings
    
    ✋
    
-   1.4
    
    Go to: **[https://github.com/Azure-Samples/python-docs-hello-world](https://github.com/Azure-Samples/python-docs-hello-world)**
    
    ✋
    
-   1.5
    
    Click on **app.py**, Check it out. Go back to **Settings** on Deployment Center, Select **Source**: GitHub, Authorize and Log into your Github account, Refresh if needed.
    
    ✋
    
-   1.6
    
    Fork the [https://github.com/Azure-Samples/python-docs-hello-world](https://github.com/Azure-Samples/python-docs-hello-world) repository to your own GitHub account
    
    ✋
    
-   1.7
    
    Enter in the settings of GitHub. Organization, Repository: **python-docs-hello-world**, Branch: **Master**. Build: **Python**
    
    ✋
    
-   1.8
    
    Save and should be ready to Deploy
    
    ✋
    

### Reference

[Quickstart: Create a Python app using Azure App Service on Linux](https://docs.microsoft.com/en-ca/azure/app-service/quickstart-python?tabs=bash&pivots=python-framework-flask)

[Create a web app in the Azure portal](https://docs.microsoft.com/en-us/learn/modules/host-a-web-app-with-azure-app-service/2-create-a-web-app-in-the-azure-portal)