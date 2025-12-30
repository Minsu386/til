Virtual Network (vNet) is a logically isolated section of the Azure Network where you launch your Azure resource

VNET peering is when you connect multiple VNet so they act as one network
**1. Regional VNet Peering** When you peer two VNets from the same region
**2. Global VNet Peering** When you peer two VNets from two different regions

**NIC**
A computer hardware component that connects a computer to a network
Communications using IP

**Azure Network Interfaces**
- Are attached to Azure VM instances
- W/ out an NIC, An Azure VM instance would have no way to communicate
- An Azure VM instance has to have a NIC and can have multiple NICs

A Route Table is a table of data stored in a router or network host that lists routes to the next destinations

By Default Azure creates a route table with defaults routes and associates them to your subnets so you don't have to do anything to get routing

You can override the system routes assigned to your subnets by creating a new route table and associating it with a subnet

**What is an Address Space**
It is a range of available IP addresses that you are allocating for you use within your VNet

The amount of IP addresses available is determined based on the CIDR range notation 

A Subnet is a logical division of an address space

A subnet needs a route table so it can access

Azure has no concept of private and public subnets and its up to you to configure our subnets to ensure they do not reach the internet by ensuring they have no route via their route table to the internet gateway

You can associate an NSG to protect traffic entering and leaving your subnet by applying security rules that can

Azure has a special type of Gateway Subnet that is used by Azure Virtual Network Gateway and that service

Azure Private Links allow you to establish secure connections between Azure resources so traffic remains within the Azure Network

Private Link Endpoint is a Network Interface that connects you privately and securely to a service powered by Azure Private Link. Private Endpoint uses a Private IP address from your VNet

Private Link Service allows you to connect your own workload to Private Link. You need an Azure Standard Internal Load Balancer and associate it with the link service
Azure Firewall is managed, cloud-based network security service that protects your Azure VNets resources

It is a Fully Stateful Firewall as a Service (FWaas) with:
- Built-In High availability
- Unrestricted Cloud Scalability
You can centrally create, enforce, and log application and network connectivity policies across subscriptions and VMs

Azure Firewall uses a static public IP address for your VNet resources allowing outside firewalls to identify traffic originating from your Virtual Network

The service is fully integrated w/ Azure monitor for logging and analytics

Traffic Filtering

Traffic is denied by default
- You launch an Azure Firewall in its own VNet
- Other VNets pass through this Central Vnet
- You get Microsoft Threat Intelligence
    - Blocks known malicious IPs and FQDNs

Azure ExpressRoutes create private connections between Azure Datacenters and infrastructure on your premises or in colocation environment

Connectivity can be from an:
- any-to-any (IP VPN) network
- a point-to-point Ethernet Network
- Virtual Cross-connection through a connectivity provider at a colocation facility

ExpressRoute Dir