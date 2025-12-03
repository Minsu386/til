Azure Scale Sets allow you to **automatically** increase or decrease your VM capacity

A Load Balancer can be associated with a Scale Set
    -Evenly distribute your VMs across multiple Availability Zones to make your application Highly Available.
    Use Load Balancer probe checks for more robust Health checks
    You have the choice between 2 different load balancer:
        1) **Application Gateway** is an HTTP/HTTPS web traffic  load balancer application firewall
        2) **Azure Load Balancer** supports all TCP/UDP network traffic, port-forwarding, and outbound flows

**A Scaling Policy** determines when a VMs should be added or removed to meet current capacity requirements
- **Scale-Out** When an instance should be added to the Scale Set to increase capacity
- **Scale-In** When an instance should be removed to the Scale Set to decrease capacity

**Scale-In Policy** is how determines what VMs is removed to decrease the capacity of the Scale Set
    - **Default** Delete the VM with the highest Instance ID, Balanced across Availability Zones (AZs) and Fault Domains (ADs)
    - **Newest VM** Delete the newest created VM, Balanced across Availability Zones (AZs)
    - **Oldest VM** Delete the oldest VM, Balanced across Availability Zones (AZs)

**Update Policy** Determines how VM instances are brought up-to-date with the latest scale set model 
-

