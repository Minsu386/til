**Azure Container Instances (ACI)** allow you to launch containers without the need to worry about configuring or managing the underlying VM.

Azure Container Instances is designed for isolate containers:
- Simple Applications
- Task Automation
- Build Jobs

Containers can be provisioned within seconds where VMs can take several minutes

Containers are **Billed per Second** Hwere VMs are billed per hour

Containers have granular and custom sizing of vCPU, Memory, and GPUs where Vms sizes are predetermined

ACI can deploy both Windows and Linux Containers

You can persist storage with Azure Files for your ACI Containers

ACIs are accessed via fully qualified domain name (FQDN) 

**Containers Groups** are a collection of containers that get scheduled on the same host machine
- The containers in a container group share: Lifecycle, Resources, local network, Storage volumes
- Containers Groups are similar to a Kubernetes pod
- Multi-container groups currently support only Linux containers

There are two ways to deploy a multi-container group:
- **Resource Manager Template (ARM Template)** - When you need to deploy additional Azure service resources
- YAML File - When your deployment includes only container instances.

A container restart policy specifies what a container should do when its process has been completed. ACI has 3 restart-policy options
- Always (Default) Containers are always restarted. Suited for long-running task eg. Web-Servers
- Never - Containers run one time only. Suited for one off task. eg. background jobs
- OnFailure - Containers that encounter an error

Azure Containers are stateless by default

When a containers crashes or stops all state is lost

To persist state, you need to mount an external volume
- You can mount the following external volumes:
    - Azure Files (file share), Secret Volume, Empty Direcotry, Cl