# Module 4 - Networking

- [Module 4 - Networking](#module-4---networking)
  - [Learning Objectives](#learning-objectives)
  - [Networking](#networking)
  - [Connectivity to AWS](#connectivity-to-aws)
    - [Public Traffic](#public-traffic)
    - [Private Traffic](#private-traffic)
  - [Subnets and Network Access Control Lists](#subnets-and-network-access-control-lists)
  - [Global Networking](#global-networking)
  - [Key Notes](#key-notes)
  - [Additional Resources](#additional-resources)

## Learning Objectives

- Describe the basic concepts of networking
- Describe the difference between public and private networking resources
- Explain a virtual private gateway using a real life scenario
- Explain a virtual private network (VPN) using a real life scenario
- Describe the benefit of AWS Direct Connect
- Describe the benefit of hybrid deployments
- Describe the layers of security used in an IT strategy
- Describe the services customers use to interact with the AWS global network

## Networking

- We need to understand the basic concepts of networking and the difference between public and private networking resources to keep our data and our client's data safe and secure.
- An **Amazon Virtual Private Cloud (Amazon VPC)** lets you provision a logically isolated section of the cloud where you can launch AWS resources in a virtual network that you define.  These resources can be public or private facing. 
- Usually for backend services like databases or application servers, the public and private grouping of resources are known as **Subnets**, which are ranged of IP addresses in your VPC
- If we had a coffee shop with a cashier and a barista, the cashier would be in the public subnet because we want them to interact with the customers and the barista would be in the private subnet to keep them away from the customers

## Connectivity to AWS

- A Virtual Private Cloud (VPC) is essentially your own private network in AWS.
- It allows you to define your private IP range for your AWS resources
- You place things like your EC2 instances and your Elastic Load Balancers in your VPC into certain Subnets
- Subnets are chunks of IP addresses in your VPC that allow you to group resources together
- Subnets along with Networking Rules control whether resources are either publicly or privately available

### Public Traffic

- In order to allow traffic from the public internet to flow into and out of your VPC, you must attach what is called an **Internet Gateway (IGW)**, to your VPC.
- An Internet Gateway is like a doorway that is open to the public.

### Private Traffic

- In order to allow traffic from only certain authorized individuals, you will need to install **Virtual Private Gateway (VPG)**, and it allows you to create a VPN connection between a private network, like your on-premises data center or internal corporate network to your VPC.
- VPN connections are private and they are encrypted, but they still use a regular internet connection that has bandwidth that is being shared by many people using the internet.
- **AWS Direct Connect**
  - **AWS Direct Connect** allows you to establish a completely private, dedicated fiber connection from your data center to AWS. 
  - You work with a Direct Connect partner in your area to establish this connection, because Direct Connect provides a physical line that connects your network to your AWS VPC. This can help you meet high regulatory and compliance needs, as well as sidestep any potential bandwidth issues. It's also important to note that one VPC might have multiple types of gateways attached for multiple types of resources all residing in the same VPC, just in different subnets.

## Subnets and Network Access Control Lists

- AWS has a ton of has a wide range of tools to cover every layer of security:
  1. **Network Hardening**
     - The only technical reason to use Subnets in a VPC is to control access to the gateways.  The Public Subnets have access to the internet gateway, but the Private Subnets do not, but Subnets can also control traffic permissions
     - **Packets** are messages from the internet.  Every packet that tries to cross the Subnet boundary gets checked across the **Network Access Control List (Network ACL)**.  This check is to see if the packet has permissions to either leave or enter the subnet based on who it was sent from and how it's trying to communicate.
     - Network ACLs check traffic coming in to and leaving the Subnet
     - Sometimes multiple instances or services run on a single Subnet, and the Network ACL can't control access to these different ports, therefore you need instance or service level security, which can be accomplished with **Security Groups**
       - Every EC2 instance when it's launched comes with a Security Group.  By default, the Security Group doesn't let any traffic into the instance at all, therefore you want to modify the Security Group to accept/deny a specific type of traffic.
         - By default, all outbound traffic is allowed with a **Security Group**
         - In the case of a website, you want web based traffic (HTTP/HTTPS), but not other types, like OS or Admin requests
     - The key difference between a **Network ACL** and a **Security Group** is that a Network ACL is **stateful**, meaning it has some kind of a memory when it comes to who to allow in or out, and the Network ACL is **stateless**, which remembers nothing and checks every single packet coming across it's border regardless of any circumstances
  2. **Application Security**
  3. **User Identity**
  4. **Authentication and Authorization**
  5. **Distributed Denial of Service (DDoS) Prevention**
  6. **Data Integrity**
  7. **Encryption**

## Global Networking

- **Amazon Route 53** is Amazon's Domain Name Service (DNS), and it is highly available and scalable
  - **Domain Name Service**'s translate website plain language addresses to IP addresses that computers can use
  - Can direct traffic through different different endpoints using several different routing policies, such as:
    1. Latency-Based Routing
    2. Geolocation DNS - Direct traffic based on where the customer is located
    3. Geoproximity Routing
    4. Weighed Round Robin
  - Can be used to register domain names, so you can buy an address on AWS
- **Amazon CloudFront** also is a key aspect of Amazon's global networking

## Key Notes

- VPC Components Examples:
  - **Private Subnet** - Isolate databases containing customers' personal information
  - **Virtual Private Gateway** - Create a VPN connection between the VPC and the internal corporate network
  - **Public Subnet** - Support the customer-facing website
  - **AWS Direct Connect** - Establish a dedicated connection between the on-premises data center and the VPC
- An AWS account's default Network Access Control List is stateless and allows all inbound and outbound traffic
- **DNS Resolution** is the translation of a domain name to an IP address
- *Your company has an application that uses Amazon EC2 instances to run the customer-facing website and Amazon RDS database instances to store customers’ personal information. How should the developer configure the VPC according to best practices?*
  - Place the Amazon EC2 instances in a public subnet and the Amazon RDS database instances in a private subnet
- **Security Group**'s are stateful and deny all inbound traffic by default
- **Internet Gateway**'s are used to connect a VPC to the internet
- **Amazon Route 53** is used to manage the DNS records for domain names

## Additional Resources

- [Amazon Virtual Private Cloud (Amazon VPC)](https://aws.amazon.com/vpc/)
- [AWS Direct Connect](https://aws.amazon.com/directconnect/)
- [Network Access Control List (Network ACL)(](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)
- [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)
- [Amazon Route 53](https://aws.amazon.com/route53)
- [Networking and Content Delivery on AWS](https://aws.amazon.com/products/networking)
- [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [What is Amazon VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [How Amazon VPC Works](https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html)