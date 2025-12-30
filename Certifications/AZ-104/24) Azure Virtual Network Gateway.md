A VPN extends a private network across a public network and enables users to send and receive data across shared or public networks as if their computing devices were directly connected to the private network
- A Virtual Network Gateway is the software VPN device for your Azure Virtual Network
- When you deploy a virtual network gateway it will deploy two or specialized VMs in specific subnet you need to create called a "gateway subnet"
- These deployed VMs contain routing tables and run specific gateway services
- You will choose a gateway Type and that will determine if it's a VPN Gateway or an ExtressRoute Gateway

When you create a VPN Gateway you are generally designing for one of the following topologies:

Site-to-Site (S2S) - When you connect Azure to an On-Prem Data Center

Multi-Site - When you connect Azure to multiple On-Prem data centers

Point-to-Site (P2S) When you connect Azure to multiple individual computers

VNet-to-VNet - When you connect two Vnets in different regions, subscriptions or deployment models