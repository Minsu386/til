**Azure Resource Manager (ARM)**: is a service that allows you to manage Azure resources.

It is a management layer that allows you to:
- Create, Update, Delete Resource
- Apply Management features eg. Access Controls, Locks, Tags
- Writing Infrastructure as Code (IaC) via JSON templates

the specific features we are going to look at that make up the ARM layer are the following:
- Subscriptions
- Management Groups
- Resource Groups
- Resource Providers
- Resource Locks
- Azure blueprints
- Resource Tags
- Access Control (IAM)
- Role-Based Access Controls (RABC)
- Azure Policies
- ARM Templates

Think of Azure Resource manager (ARM) as a gate keeper.

All requests flow through ARM and it decides whether that request can be performed on a resource.

Scope is a Boundary of control for azure resources. It is a way to govern your resource by placing resources
- within a logical grouping
- and also applying logical restrictions in the form of rules.

**Management Groups** - A Logical grouping of multiple subscriptions

**Subscriptions**: - Grants you access to Azure services based on a billing and support agreement

**Resource Groups** - A logical grouping of multiple resources

**Resources** - An Azure service eg. Azure VMs

**Resource Providers** - A list of possible services within Azure, some services are registered by default and others need to explicitly be registered.

**Resource Tags** - Are a Key and Value pair that you can assign to Azure resources

Resource locks prevent users from accidentally modifying for deleting resources at the Subscription, Resource Group or Resource Scope


**CanNotDelete** - Authorized users can still read and modify a resource, but they can't delete the resource.

**ReadOnly** - Authorized users can read a resource, but they can't delete or update the resource

**Azure Blueprints** - Enables Quick creation of governed subscriptions.
- Relationship between the blueprint definition (what should be deployed) and the blueprint assignment (what was deployed)
- Can also upgrade several subscription at once that are governed by the same blueprint