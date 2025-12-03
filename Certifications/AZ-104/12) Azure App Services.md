**Azure App Service** is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends.
- You can choose your **programming language** and either a **Windows** and **Linux** environment
- It is a Platform as a Service, so it's the heroku or AWS Elastic Beanstalk equivalent for Azure

**Azure App Service** makes it easy to implement common integrations and features such as:
- Azure DevOps (For deployments)
- Github Integration
- Docker Hub Integration
- Package Management
- Easy to setup staging environments
- Custom Domains
- Attaching TLS/SSL Certificates

You pay based on an Azure App Service Plan:
- **Shared Tier**: Free, Shared (Linux not supported)
- **Dedicated Tier**: Basic, Standard, Premium, PremiumV2, PremiumV3
- **Isolated Tier**

Azure app Services support the following runtimes: .NET, .NET Core, Java, Ruby, Node.js, PHP, Python


Azure App Services can also run **Docker** single or multi-containers
- **Custom Containers** are supported, create docker files, upload to Azure Container Registry and deploy

**Deployments Slots** allow you to create different environment of your web-application
- You can also Swap **environments** this could be how you perform a Blue/Green deployment

**App Service Environment (ASE)** is an Azure App Service feature that provides a **fully isolated and dedicated environment** for securely running App Service apps at high scale
- Customers can create multiple ASEs:
    - within a single Azure region
    - Across multiple Azure regions making ASEs
- Ideal for Horizontally scaling stateless applications tiers in support of high requests per second (RPS) workloads
- ASE come with its own pricing tier (Isolated Tier)
- ASEs can be used to configure security architecture
- Apps running on ASEs can have their access gated by upstream devices, such as web application firewalls (WAFs)
- App Service Environments can be deployed into Availability Zones (AZ) using zone pinning. 
- There are 2 deployment types for an App Service Environments (ASE): 
    - 1) External ASE
    - 2) ILB ASE

Azure App Services provides many ways to deploy your applications:
**WebJobs** is a feature of Azure App Service that enables you to run a program or script in the sam einstance as a web app, API app or mobile app
- There is no additional cost to use WebJobs