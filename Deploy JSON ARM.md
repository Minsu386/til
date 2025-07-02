
# Deploy Azure Infrastructure by using JSON ARM templates
## Pre Req
- Familiarity with Azure, including the Azure portal, subscriptions, resource groups, and resource definitions
- An Azure account. You can get a free account [here](https://azure.microsoft.com/free?azure-portal=true)
- [Visual Studio Code](https://code.visualstudio.com/?azure-portal=true) installed locally
- The [Azure Resource Manager Tools for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools&azure-portal=true) extension installed locally
- Either:
    - The latest [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli?azure-portal=true) tools installed locally
    - The latest [Azure PowerShell](https://learn.microsoft.com/en-us/powershell/azure/install-az-ps?azure-portal=true) installed locally


## ARM Template File structure

| Element            | Description                                                                                                                                                                                                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **schema**         | A required section that defines the location of the JSON schema file that describes the structure of JSON data. The version number you use depends on the scope of the deployment and your JSON editor.                                                                                                                                  |
| **contentVersion** | A required section that defines the version of your template (such as 1.0.0.0). You can use this value to document significant changes in your template to ensure you're deploying the right template.                                                                                                                                   |
| **apiProfile**     | An optional section that defines a collection of API versions for resource types. You can use this value to avoid having to specify API versions for each resource in the template.                                                                                                                                                      |
| **parameters**     | An optional section where you define values that are provided during deployment. You can provide these values in a parameter file, by command-line parameters, or in the Azure portal.                                                                                                                                                   |
| **variables**      | An optional section where you define values that are used to simplify template language expressions.                                                                                                                                                                                                                                     |
| **functions**      | An optional section where you can define [user-defined functions](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/template-user-defined-functions) that are available within the template. User-defined functions can simplify your template when complicated expressions are used repeatedly in your template. |
| **resources**      | A required section that defines the actual items you want to deploy or update in a resource group or a subscription.                                                                                                                                                                                                                     |
| **output**         | An optional section where you specify the values that are returned at the end of the deployment.                                                                                                                                                                                                                                         |


## Deploy
``` Azure CLI
az login
```

``` PowerShell
Connect-AzAccount
```

Define your resource group. You can obtain available location values from : `az account list-location` CLI or `Get-AzLocation` PowerShell.  You can config the default location using `az configure --defaults location=<location>`

```azure cli
az deployment group create --name {name of your resource group} --location "{location}"
```

```PowerShell
New-AzResourceGroup -Name {name of your resource group} -Location "{location}"
```



[AZ-104](Certifications/AZ-104.md)



