Azure Kubernetes Service (AKS) makes it simple to deploy a managed Kubernetes cluster in Azure

Azure will manage for you the:
- Kubernetes masters
- Health monitoring
- maintenance

You only have to maintain the: Agent Nodes

AKS service is free, You only pay for the agent nodes within the cluster, not the masters

You should use AKS for scenarios where you need full container orchestration:
- Service discovery across multiple containers
- automatic scaling
- coordinated application upgrades
Bridge to Kubernetes is an extension in Visual Studio and VSC that allows developers to write, test, and debug microservice code on their development workstation