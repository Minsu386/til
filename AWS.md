Amazon Web Services

Cover over 30 [AWS](AWS.md) Services


## Global Infrastructure
- Regions
- Availability Zones
- Data Cetners
- Edge Locations / Points of Presense
- https://infrastructure.aws/


### Region
----
- All around the world
- name can be us-east-1 | eu-west-3
- region is a cluster of data center
- Most AWS services are region based

How to choose an AWS Region?
- depends - factors - 
	- Compliance - w/ data gov't and legal requirements: data never leaves a region without your explicit permission
	- Proximity to customers: reduced latency
	- Available services  within a Region: New services and new features aren't available in every region
	- Pricing: Varies region to region and is transparent in the service pricing page

### Availability Zones
----
Each region has many availability zones (usually 3, min is 3, max is 6) Examples:
- ap-southeast-2a
- ap-southeast-2b
- ap-southeast-2c

![](AWS%20Region.jpg)

- Each Availability zone (AZ) is 1 or more discrete DC w/ redundant pwr, networking, and connectivity.
- They're are separate from each other, so that they're isolated from disasters.


aws.amazon.com/about-aws/global-infrastructure/


## IAM: Users & Groups
----

- IAM = Identity and Access Management, **Global** service
- Root account created by default, shouldn't be used or shared
- **Users** are people within your organization, and can be grouped
- **Groups** only contain users, not other groups
- Users don't have to belong to a group, and user can belong to multiple groups
![](AWS_IAM_Users_Groups.jpg)


### IAM: Permissions
----

- **Users or Groups** can be assigned JSON documents called policies
- Policies define the **permissions** of the users
- in AWS you apply the **least privilege principle**: 


IAM USER login is preferred than ROOT User