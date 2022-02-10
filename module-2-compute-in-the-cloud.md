# Module 2 - Compute in the Cloud

- [Module 2 - Compute in the Cloud](#module-2---compute-in-the-cloud)
  - [Learning Objectives](#learning-objectives)
  - [Amazon Elastic Compute Cloud (Amazon EC2)](#amazon-elastic-compute-cloud-amazon-ec2)
    - [Amazon EC2 Configurations](#amazon-ec2-configurations)
    - [Amazon EC2 Overview](#amazon-ec2-overview)
    - [How Amazon EC2 Works](#how-amazon-ec2-works)
    - [Amazon EC2 Instance Types](#amazon-ec2-instance-types)
    - [Amazon EC2 Pricing](#amazon-ec2-pricing)
    - [Amazon EC2 Scaling](#amazon-ec2-scaling)
      - [Amazon EC2 Auto Scaling](#amazon-ec2-auto-scaling)
  - [Directing Traffic with Elastic Load Balancing](#directing-traffic-with-elastic-load-balancing)
  - [Messaging and Queueing](#messaging-and-queueing)
    - [Amazon Simple Queue Service (Amazon SQS)](#amazon-simple-queue-service-amazon-sqs)
    - [Amazon Simple Notification Service (Amazon SNS)](#amazon-simple-notification-service-amazon-sns)
  - [Additional Compute Services](#additional-compute-services)
    - [Serverless](#serverless)
    - [Container Services](#container-services)
  - [When To Use What](#when-to-use-what)
  - [Trivia](#trivia)
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

### Amazon EC2 Overview

- Imagine you are responsible for the architecture of your company's resources and need to support new websites.  With tradition on-premises resources, you have to do the following:
  - Purchase hardware
  - Wait for the servers to arrive
  - Install the servers in a physical location 
  - Make necessary configurations
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

### Amazon EC2 Instance Types

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

### Amazon EC2 Pricing

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

### Amazon EC2 Scaling

- **Scalability** involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling in or out.  As a result, you pay for only the resources you use.
- You can achieve automatic scaling by using the AWS service **Amazon EC2 Auto Scaling**

#### Amazon EC2 Auto Scaling

- If you've ever tried to access a website that wouldn't load and frequently timed out, the website might have received more requests than it was able to handle.  This situation is similar to waiting in a long line a coffee shop, where there is only one barista to take orders from customers.
- Amazon EC2 Auto Scaling enables you to automatically add or remove EC2 instances in response to changing application demand.  By Automatically scaling your instances in and out as needed, you are able to maintain a greater sense of application availability and will only pay for what you use.
- **Dynamic Scaling** - Responds to changing demand
- **Predictive Scaling** - Automatically schedules the right number of Amazon EC2 instances based on the predicted demand
- To scale faster, you can use dynamic scaling and predictive scaling together.
- There are two types of scaling, ***up*** and ***out***
  - **Up** - Adding more power to the machines that are running
  - **Out** - Adding more instances to the host
- When you create an Auto Scaling group, you can set the **minimum number**, **maximum number**, and **desired capacity** of EC2 instances
  - If you do not specify the desired number of Amazon EC2 instances in an Auto Scaling group, the desired capacity defaults to your minimum capacity.

## Directing Traffic with Elastic Load Balancing

- **Elastic Load Balancing** is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.  Utilizing Elastic Load Balancing with Auto Scaling groups allows you to properly distribute traffic in a high performance, cost-efficient, highly available, automatically scalable way.
- A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group.  This means that as you add or remove EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first.  Then, the requests spread across multiple resources that will handle them.
- Elastic Load Balancing is a **Regional Construct**, which is a higher level than individual EC2 instances, allowing it to automatically be highly available with little effort on your part
- We can use Elastic Load Balancing to properly distribute traffic between the Front End and Back End as well, creating de-coupled architecture

## Messaging and Queueing

- If applications communicate directly, we call it, **Tightly Coupled Architecture**.  A hallmark of tightly coupled architecture is that if one component of the applications fails, it causes other components or the whole system to fail
- **Loosely Coupled Architecture** is a much better design pattern.  It is where a single failure won't cause cascading failures
  - By adding a **Message Queue** between two applications, we create a buffer between our applications.  If applications B fails, applications A doesn't experience a disruption.  Messages from application A will just keep getting passed to the Message Queue until application B is back online to process them

### Amazon Simple Queue Service (Amazon SQS)

- Allows you to send, store, and receive messages between software components at any volume without losing messages or requiring any other service to be immediately available
- A good example is a coffee shop.  Our cashier would be an EC2 instance (server) who passes the customer's (client) order to an order board (Amazon SQS) that the barista (server) will process when available
- Data contained within a message is called a **payload** and is protected until delivery
- These scale automatically, are reliable, and are easily configured and used

### Amazon Simple Notification Service (Amazon SNS)

- Similar to SQS in that it is used to send out messages to services, but it can also send out notifications to end users
- It does this in a different way, **Publishing and Subscribing** in what is called a **Pub/Sub Model**
- You can create **SNS Topics**, which is simple a channel for messages to be delivered.  You then configure subscribers to that topic and find the published messages for those subscribers. 
- In practice, this means you can send one message to a topic and have it span out to all of the topic's subscribers.
- These subscribers can also be endpoints, meaning they can be things such as *SQS Queues*, *Lambda Functions*, and *HTTP/HTTPS Web Hooks*
- Additionally SNS can be used to fan out messages to end users via Mobile Push, SMS, and Email

## Additional Compute Services

- EC2 requires that you set up and manage your fleet of instances over time.  When using EC2, you're responsible for patching your instances when new software packages come out, setting up the scaling of those instances, as well as ensuring that you've architected your solutions to be hosted in a highly available manner.

### Serverless

- Serverless means you cannot see or access the underlying infrastructure/instances hosting your application.  With serverless computing, you can focus more on innovating new products and features instead of maintaining servers. Another benefit of serverless computing is the flexibility to scale serverless applications automatically. Serverless computing can adjust the applications' capacity by modifying the units of consumptions, such as throughput and memory.
- **AWS Lambda**
  - While using AWS Lambda, you pay only for the compute time that you consume. Charges apply only when your code is running. You can also run code for virtually any type of application or backend service, all with zero administration.
  - Designed to run for less than 15 minutes
  - **Process**
    - Upload code to Lambda
    - Set your code to trigger from an event source, such as AWS services, mobile applications, or HTTP endpoints.
    - Code runs only when triggered
    - Pay only for the compute time you use

### Container Services

- A container in this scenario is a Docker container.  A container can be considered a package for your code
- A **Cluster** is a number of EC2 instances running containers that are in communication with each other
- **Amazon Elastic Container Service (Amazon ECS)**
  - Designed to run your container applications at scale without the hassle of using **container orchestration** software
  - With Amazon ECS, you can use API calls to launch and stop Docker-enabled applications.
- **Amazon Elastic Kubernetes Services (Amazon EKS)**
  - Does something similar to ECS, but with different tooling and features
  - Kubernetes is open-source software that enables you to deploy and manage containerized applications at scale
- Both ECS and EKS can run on top of EC2 instances
- **Amazon Fargate**
  - A serverless compute platform for ECS or EKS

## When To Use What

- **Amazon EC2**
  - When you want to host traditional applications and need full access to the OS
- **AWS Lambda**
  - Hosting short running functions
  - Service-oriented applications
  - Event driven applications
  - No provisioning or managing servers
- **Amazon ECS/EKS**
  - Run Docker container-based workloads on AWS
  - **Amazon EC2/AWS Fargate**
    - You need to choose if you want to manage your instance with EC2 or allow Fargate to manage it serverlessly for you

## Trivia

- Which AWS service is the best choice for publishing messages to subscribers?
  - Amazon Simple Notification Service (Amazon SNS)
- You want to use an Amazon EC2 instance for a batch processing workload. What would be the best Amazon EC2 instance type to use?
  - Compute Optimized
- What are the contract length options for Amazon EC2 Reserved Instances?
  - 1-year and 3-year
- You have a workload that will run for a total of 6 months and can withstand interruptions. What would be the most cost-efficient Amazon EC2 purchasing option?
  - Spot instance
- What is the process of Elastic Load Balancing?
  - Ensuring that no single Amazon EC2 instance has to carry the full workload on its own
- You want to deploy and manage containerized applications. Which service should you use?
  - Amazon EKS/ECS

## Additional Resources

- [Amazon EC2 instance types](https://aws.amazon.com/ec2/instance-types/)
- [Amazon SNS](https://aws.amazon.com/sns)
- [Compute on AWS](https://aws.amazon.com/products/compute)
- [AWS Compute Blog](https://aws.amazon.com/blogs/compute/)
- [AWS Compute Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
- [Hands-On Tutorials: Compute](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute&awsf.getting-started-content-type=content-type%23hands-on)
- [Category Deep Dive: Serverless](https://aws.amazon.com/getting-started/deep-dive-serverless/)
- [AWS Customer Stories: Serverless](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23serverless)