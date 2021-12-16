# Module 1 - Introduction to Amazon Web Services

- [Module 1 - Introduction to Amazon Web Services](#module-1---introduction-to-amazon-web-services)
  - [Learning Objectives](#learning-objectives)
  - [Introduction](#introduction)
    - [Services](#services)
    - [Cloud Compute Model](#cloud-compute-model)
    - [Server Instances](#server-instances)
  - [Cloud Computing](#cloud-computing)
    - [Deployment Models for Cloud Computing](#deployment-models-for-cloud-computing)
    - [Benefits of Cloud Computing](#benefits-of-cloud-computing)
    - [Additional Resources](#additional-resources)
  - [Notes](#notes)

## Learning Objectives

- Summarize the benefits of AWS
- Describe the differences between on-demand delivery and cloud deployments
- Summarize the pay-as-you-go pricing model

## Introduction

- AWS - Only pay for what you use

### Services

- Computing
- Storage
- Network Security
- Blockchain
- Machine Learning
- Artificial Intelligence
- Robot Development
- Video Production
- Orbital Satellites

### Cloud Compute Model

Almost all modern computing centers around a basic client/server model.  Basically a customer makes a request, and the server will serve that request. In computing, a client can be a web browser or desktop application that a person interacts with to make requests to computer servers. A server can be services such as Amazon Elastic Compute Cloud (Amazon EC2), a type of virtual server.

### Server Instances

- Amazon EC2 (Elastic Cloud Computer).  A virtual machine/server

## Cloud Computing

- Cloud computer is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing that are ready to use when you need them
- The goal of AWS is to create services to automate repetitive, monotonous tasks so that you can focus more on what you want to offer your clients

### Deployment Models for Cloud Computing

- When selecting a cloud strategy, a company must consider factors such as required cloud application components, preferred resource management tools, and any legacy IT infrastructure requirements.
- The three cloud computing deployment models are cloud-based, on-premises, and hybrid
  - **Cloud-Based Development**
    - Runs all parts of the application from the cloud
    - Migrate existing applications to the cloud
    - Design and build new applications in the cloud
    - In a **cloud-based deployment** model, you can migrate existing applications to the cloud, or you can design and build new applications to the cloud.  You can build those applications on low-level infrastructure that requires your IT staff to manage them.  Alternatively, you can build them using higher-level services that reduce the management, architecting, and scaling requirements of the core infrastructure
    - For example, a company might create an application consisting of virtual servers, databases, and networking component that are fully based in the cloud
  - **On-Premises Deployment**
    - Deploy resources by using virtualization and resource management tools
    - Increase resource utilization by using application management and virtualization technologies
    - **On-premises deployment** is also known as a *private cloud* deployment.  In this model, resources are deployed on premises by using virtualization and resource management tools.
    - For example, you might have applications that run on technology that is fully kept in your on-premises data center.  Though this model is much like legacy IT infrastructure, it's incorporation of application management and virtualization technologies helps to increase resource utilization
  - **Hybrid Deployment**
    - Connect cloud-based resources to on-premises infrastructure
    - Integrate cloud-based resources with legacy IT applications
    - In a **hybrid development**, cloud-based resources are connected to on-premises infrastructure.  You might want to use this approach in a number of situations.  For example, you have legacy applications that are better maintained on premises, or government regulations require your business to keep certain records on premises
    - For example, suppose that a company wants to use cloud services that can automate batch data processing and analytics.  However, the company has several legacy applications that are more suitable on premises and will not be migrated to the cloud.  With a hybrid deployment, the company would be able to keep the legacy applications on premises while benefiting from the data and analytics services that run in the cloud 

### Benefits of Cloud Computing

Consider why a company might choose to take a particular cloud computing approach when addressing business needs.

- **Trade upfront expense for variable expense**
  - Upfront expense refers to data centers, physical servers, and other resources that you would need to invest in before using them.  Variable expense means you only pay for computing resources you consume instead of investing heavily in data centers and servers before you know how you're going to use them
  - By taking a cloud computing approach that offers the benefit of variable expense, companies can implement innovative solutions while saving on costs
- **Stop spending money to run and maintain data centers**
  - Computing in data centers often requires you to spend more money and time managing infrastructure and servers
  - A benefit of cloud computing is the ability to focus less on these tasks and more on your applications and customers
- **Stop guessing capacity**
  - With cloud computing, you don't have to predict how much infrastructure capacity you will need before deploying an application
  - For example, you can launch Amazon EC2 instances when needed, and only pay for the compute time you use.  Instead of paying for unused resources or having to deal with limited capacity, you can access only the capacity that you need.  You can also scale in or out in response to demand
- **Benefit from massive economies of scale**
  - By using cloud computing, you can achieve a lower variable cost than you can get on your own
  - Because usage from hundreds of thousands of customers can aggregate in the cloud, providers, such as AWS, can achieve higher economies of scale.  The economy of scale translates into lower pay-as-you-go prices
- **Increase speed and agility**
  - The flexibility of cloud computing makes it easier for you to develop and deploy applications
  - This flexibility provides you with more time to experiment and innovate.  When computing in data centers, it may take weeks to obtain new resources that you need.  By comparison, cloud computing enables you to access new resources within minutes
- **Go global in minutes**
  - The global footprint of the AWS Cloud enables you to deploy applications to customers around the world quickly, while providing them with low latency.  This means that even if you are located in a different part of the world than your customers, customers are able to access your applications with minimal delays

### Additional Resources

- [AWS Glossary](https://docs.aws.amazon.com/general/latest/gr/glos-chap.html)
- [Whitepaper: Overview of Amazon Web Services](https://d0.awsstatic.com/whitepapers/aws-overview.pdf)
- [AWS Fundamentals: Overview](https://aws.amazon.com/getting-started/fundamentals-overview/)
- [What is cloud computing?](https://aws.amazon.com/what-is-cloud-computing/)
- [Types of cloud computing](https://aws.amazon.com/types-of-cloud-computing/)
- [Cloud computing with AWS](https://aws.amazon.com/what-is-aws/)

## Notes

- **What is cloud computing?**
  - On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing
- **What is another name for on-premises deployment?**
  - Private cloud deployment
- **How does the scale of cloud computing help you to save costs?**
  - The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices.