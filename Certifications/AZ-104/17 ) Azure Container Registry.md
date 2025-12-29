Azure Container Registry is a managed, private Docker registry service based on the open-source Docker Registry 2.0

Use Azure Container Registries with your existing container development and deployment pipelines

Use Azure Containers Registry Tasks to build containers images in Azure

Pull Images from an Azure container registry to various deployment targets:
- Kubernetes
- DC/OS
- Docker Swam

Azure Containers Registry (ACR) Tasks allow you to automate OS and framework patching for your Docker Conainers
- You can trigger automated builds by:
    - source code updates
    - updates to a container's base image
    - Timers on a schedule
- You can create multi-step tasks
- Each ACR Task has an associated source code context
- Tasks can take advantage of run variables
