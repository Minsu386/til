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