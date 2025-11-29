**Infrastructure As Code (IaC)** - is the process of managing and provisioning computer data centers through machine-readable definition files (eg JSON files) rather than physical hardware configuration or interactive configuration tools

**IaC** can either be:
**Declarative** - You defined exactly what you want, and what you get exactly that

**Imperative** - You define what you generally want, and the service will guess what you want

**ARM Templates** - JSON files that define azure resources you want to provision and azure services you want to configure
- They are declarative. (you get exactly what you define)

**$schema** - describes the properties that are available within a template

**contentVersion** - The version of the template. You can provide any value for this element

**apiProfile** - Use this value to avoid having to specify API version for each resource in the template

**parameters** - values you can pass along to your template

**variables** - You transform parameters or resource properties using function expressions

**functions** - User-Defined functions available within the template

**resources** - the azure resources you'll want to deploy or update
-  **type** - Type of the resource
- **apiVersion** - Version of the REST API to use for the resource. Each resource provider published its own API version
- **name** - Name of the resource
- **Location** - Most resources have a location property. The region where the resource will be deployed
- **Other Properties** - Other properties we can use to configure the resource. Will vary per resource type

**Outputs** - values that are returned after deployment
