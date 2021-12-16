# Module 2 - Compute in the Cloud

- [Module 2 - Compute in the Cloud](#module-2---compute-in-the-cloud)
  - [Learning Objectives](#learning-objectives)
  - [Amazon Elastic Compute Cloud (Amazon EC2)](#amazon-elastic-compute-cloud-amazon-ec2)
    - [Amazon EC2 Configurations](#amazon-ec2-configurations)

## Learning Objectives

- Describe the benefits of Amazon EC2 at a basic level
- Identify the different Amazon EC2 instance types
- Differentiate between the various billing options for Amazon EC2
- Summarize the benefits of Amazon EC2 Auto Scaling
- Summarize the benefits of Elastic Load Balancing
- Give an example of the uses for Elastic Load Balancing
- Summarize the differences between Amazon Simple Notification Services (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS)
- Summarize additional AWS compute options

## Amazon Elastic Compute Cloud (Amazon EC2)

- Amazon EC2 provides secure, resizable compute capacity in the cloud as Amazon EC2 instances
- It is highly flexible, cost-effective, and fast compared to running your own servers on-premises
- **Hypervisor** - A program used to run and manage one or more virtual machines on a computer
  - **Multitenancy** - Sharing underlying hardware between virtual machines.  Hypervisors manage this
  - Although multiple EC2 instances run off the same host, they are unaware of each other and don't have access to each other, keeping your applications secure
  
### Amazon EC2 Configurations

- You can choose the OS of your EC2 instances:
  - Windows
  - Linux
- You can also choose the software your EC2 instances should run:
  - Internal business apps
  - Web Apps
  - Databases
  - Third-party software
- Amazon EC2 instances are scalable.  You can start with a small instance, and make it larger or smaller as needed.  This is known as **vertical scaling**
- You also control the networking of your EC2 instance.  It can be private, public, or accessible by only certain individuals and teams