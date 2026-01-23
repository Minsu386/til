## Create a Kubernetes Cluster

**Section 1 - Create Kubernetes cluster and create deployment nginx**

-   1.1
    
    Go to subscriptions, go to Resource Providers, search for "Kubernetes", Register **Microsoft.Kubernetes** and **Microsoft.KubernetesConfiguration**
    
    ✋
    

or Use PowerShell

-   Click on Cloud Shell, Use PowerShell, enter in **az**, **az account show --output table**
-   [Get-AzResourceProvider](https://docs.microsoft.com/en-us/powershell/module/az.resources/get-azresourceprovider?view=azps-6.3.0)
-   Enter in **Get-AzResourceProvider**
-   Enter in **Get-AzResourceProvider -ProviderNamespace Microsoft.Kubernetes**
-   Enter in **Register-AzResourceProvider -ProviderNamespace Microsoft.Kubernetes**
-   Enter in **Register-AzResourceProvider -ProviderNamespace Microsoft.KubernetesConfiguration**

It may take some time to register

-   1.2
    
    Search for **Kubernetes services** and go to Kubernetes services, +Create a Kubernetes Cluster
    
    ✋
    

Enter in information

-   Create a new resource group: borg
-   Kubernetes cluster name: borg
-   Region: East US
-   Kubernetes version: 1.20.7 (Default version)
-   Size: Standard DS2 v2, or any other size you are comfortable with is fine since we will be deleting it after
-   Scale method: Make sure this is Manual so we can scale it with Powershell later. Although Automatic is recommended!
-   Node count range: 1-3

Click Review and Create

-   1.3
    
    Go to [az aks](https://docs.microsoft.com/en-us/cli/azure/aks?view=azure-cli-latest) for the commands of az aks in PowerShell
    
    ✋
    
-   1.4
    
    Enter in **az aks nodepool list --resource-group 'borg' --cluster-name 'borg' --output table**
    
    ✋
    
-   1.5
    
    Go to [az aks get-credentials](https://docs.microsoft.com/en-us/cli/azure/aks?view=azure-cli-latest#az_aks_get_credentials)
    
    ✋
    
-   1.6
    
    Enter in **az aks get-credentials --name 'borg' --resource-group 'borg'**
    
    ✋
    
-   1.7
    
    Enter in **kubectl get nodes**
    
    ✋
    
-   1.8
    
    Enter in **kubectl create deployment nginx --image=nginx** (from [https://hub.docker.com/\_/nginx](https://hub.docker.com/_/nginx))
    
    ✋
    
-   1.9
    
    Enter in **kubectl get pods**
    
    ✋
    
-   1.10
    
    Enter in **kubectl get deployment**
    
    ✋
    
-   1.11
    
    Enter in **kubectl expose deployment nginx --port=80 --type=LoadBalancer**
    
    ✋
    
-   1.12
    
    Enter in **kubectl get service**, copy the External-IP, and test nginx
    
    ✋
    

**Section 2 - Create httpd image deployment**

-   2.1
    
    Enter in **kubectl create deployment httpd --image=httpd** (from [https://hub.docker.com/\_/httpd](https://hub.docker.com/_/httpd))
    
    ✋
    
-   2.2
    
    Enter in **kubectl get pods**
    
    ✋
    
-   2.3
    
    Enter in **kubectl get deployment**
    
    ✋
    
-   2.4
    
    Enter in **kubectl expose deployment httpd --port=80 --type=LoadBalancer**
    
    ✋
    
-   2.5
    
    Enter in **kubectl get service**, copy the External-IP of httpd and test it
    
    ✋
    

**Section 3 - kubectl scale**

-   3.1
    
    Enter in **kubectl scale --replicas=3 deployment/httpd**
    
    ✋
    
-   3.2
    
    Enter in **kubectl get pods**
    
    ✋
    
-   3.3
    
    Enter in **az aks scale --resource-group 'borg' --name 'borg' --node-count 3** (try 2 if 3 does not work)
    
    ✋
    
-   3.4
    
    Enter in **kubectl get pods**
    
    ✋
    
-   3.5
    
    Enter in **kubectl get pod -o=custom-columns=NODE:.spec.nodeName,POD:.metadata.name**
    
    ✋
    
-   3.6
    
    Go to the borg kubernetes service, click on Workloads to see the nginx and httpd deployments and the pods tab, explore around to get familiar with kubernetes service
    
    ✋
    
-   3.7
    
    Enter in **kubectl delete deployment nginx**, **kubectl delete deployment httpd**
    
    ✋
    
-   3.8
    
    Delete **borg** kubernetes cluster
    
    ✋