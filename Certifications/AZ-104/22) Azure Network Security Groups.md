A Network Security Group (NSG) controls inbound and outbound network traffic to and from Azure resources with a Virtual Network (VNet)

An NSG is made up of security rules:
- Name - A unique ID for the NSG
- Source or Destination - Specifies the origin or target of traffic. Can be an IP Address, CIDR block, Service Tag, or Application Security Group (ASG)
- Port Range - Defines one or more ports (e.g., 80,443, or ranges like 10000-10005)
- Protocol - TCP, UDP, ICMP, or ANY
- Action - Allow or Deny network traffic
- Priority - A number between 100 and 4096. Lower numbers are processed first
- Direction:
    - Inbound Rule - Apply to traffic entering the NSG
    - Outbound Rule - Apply to traffic leaving the NSG

Default Behavior:
- Azure creates default inbound and outbound rules when an NSG is deployed
- You cannot create two security rules with the same priority and direction

Key Facts:
- Each NSG can have up to 1,000 rules
- You can create up to 5,000 NSG per subscription
- Rules are processed in priority order
- NSGs are stateful:
    - if inbound traffic is allowed, the corresponding outbound response is automatically allowed
    - If outbound traffic is allowed, the corresponding inbound response is permitted