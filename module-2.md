# Module 2 - Compute in the Cloud

- [Module 2 - Compute in the Cloud](#module-2---compute-in-the-cloud)
  - [Learning Objectives](#learning-objectives)
  - [Amazon Elastic Compute Cloud (Amazon EC2)](#amazon-elastic-compute-cloud-amazon-ec2)
  - [Amazon EC2 Configurations](#amazon-ec2-configurations)
  - [Amazon EC2 Overview](#amazon-ec2-overview)
    - [How Amazon EC2 Works](#how-amazon-ec2-works)
  - [Amazon EC2 Instance Types](#amazon-ec2-instance-types)
  - [Amazon EC2 Pricing](#amazon-ec2-pricing)
  - [Additional Resources](#additional-resources)

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
  
## Amazon EC2 Configurations

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

## Amazon EC2 Overview

- Imagine you are responsible for the architecture of your company's resources and need to support new websites.  With tradition on-premises resources, you have to do the following:
  - Spend money upfront to purchase hardware
  - Wait for the servers to arrive
  - Install the servers in a physical location
  - Make all the necessary configurations
- By comparison, with an Amazon EC2 instance you can use a virtual server to run applications in the AWS Cloud
  - You can provision and launch an Amazon EC2 instance within minutes
  - You can stop using it when you have finished running a workload
  - You pay only for the compute time you use when an instance is running, not when it is stopped or terminated
  - You can save costs by paying only for server capacity that you need or want

### How Amazon EC2 Works

1. **Launch**
   - First, you launch an instance.  Begin by selecting a template with basic configurations for your instance.  These configurations include the OS, application server, or applications.  You also select the instance type, which is the specific hardware configuration for your instance.
   - As you are preparing to launch an instance, you specify security settings to control the network traffic that can flow into and out of your instance.
2. **Connect**
   - Next, connect to the instance.  You can connect to the instance in several ways.  Your programs and applications have multiple different methods to connect directly to the instance and exchange data.  Users can also connect to the instance by logging in and accessing the computer desktop
3. **Use**
   - After you have connected to the instance, you can begin using it.  You can run commands to install software, add storage, copy and organize files, and more.

## Amazon EC2 Instance Types

Each Amazon EC2 instance type is grouped under an instance family, which are optimized for certain types of tasks.  They offer different types of CPU, Storage, Networking, and Security features based on what you need.

- **EC2 Instance Families**
  - **General Purpose**
    - Balanced resources
    - Can be used for a variety of diverse workloads such as web servers or code repositories
  - **Compute Optimized**
    - For compute intensive tasks such as gaming servers, High performance computing (HPC), and scientific modeling
  - **Memory Optimized** - For memory intensive tasks
  - **Accelerated Computing**
    - Good for floating point number calculations, graphics processing, or data pattern matching
    - Utilizes hardware accelerators
  - **Storage Optimized** - Good for high performance on locally stored data

## Amazon EC2 Pricing

- Amazon EC2 has multiple purchasing options:
  - **On-Demand**
    - Only pay for what you run.  No long term commitments or contracts are needed.  This is great for when you're just getting started
  - **Savings Plans**
    - Offers low prices on EC2 usage in exchange for a commitment measured in dollars per hour for a 1-year or 3-year term
    - Very flexible and can provide savings of up to 72%
  - **Reserved Instances**
    - Used for steady state workloads or workloads with predictable usage and can offer up to a 75% discount (1 or 3-year term)
    - Can be paid *all upfront*, *partial upfront*, *no upfront*
  - **Spot Instances**
    - Request spare Amazon EC2 instance capacity for up to 90% off the on-demand price
    - Amazon can reclaim the instance any time they need, and they give you a 2 minute warning
    - Good for batch workloads
  - **Dedicated Hosts**
    - Used for meeting certain compliance requirements and no one else will share your host

## Additional Resources

[Amazon EC2 instance types](https://aws.amazon.com/ec2/instance-types/)