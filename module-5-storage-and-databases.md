# Module 5 - Storage and Databases

## Learning Objectives

- Summarize the basic concept of storage and databases.
- Describe the benefits of Amazon Elastic Block Store (Amazon EBS).
- Describe the benefits of Amazon Simple Storage Service (Amazon S3).
- Describe the benefits of Amazon Elastic File System (Amazon EFS).
- Summarize various storage solutions.
- Describe the benefits of Amazon Relational Database Service (Amazon RDS).
- Describe the benefits of Amazon DynamoDB.
- Summarize various database services.

## Instances Stores and Amazon Elastic Block Store (Amazon EBS)

- When you're using Amazon EC2 to run your business applications, those applications need access to CPU, memory, network, and storage. EC2 instances give you access to all those different components. As applications run, they will often need access to block-level storage.
- You can think of block-level storage as a place to store files. A file being a series of bytes that are stored in blocks on disc. When a file is updated, the whole series of blocks aren't all overwritten. **Instead, it updates just the pieces that change.** This makes it an **efficient storage type when working with applications like databases, enterprise software, or file systems**.
- When you launch an EC2 instance, depending on the type of the EC2 instance you launched, it might provide you with local storage called instance store volumes. These volumes are physically attached to the host, your EC2 instances running on top of. And you can write to it just like a normal hard drive. The catch here is that since this volume is attached to the underlying physical host, if you stop or terminate your EC2 instance, **all data written to the instance store volume will be deleted**.

### Instance Stores

Block-level storage volumes behave like physical hard drives

- An **instance store** provides temporary block-level storage for an Amazon EC2 instance.  An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance.  When the instance is terminated, you lose any data in the instance store.

- **Amazon Elastic Block Store (Amazon EBS)** is a service that provides block-level storage volumes that you can use with EC2 instances.  If an EC2 instance is stopped or terminated, data will persist on an EBS volume.
  - To create an EBS volume, you define the configuration (such as volume size and type) and provision it.  After you create an EBS volume, it can attach to an EC2 instance
  - Because EBS volumes are for data that needs to persist, it's important to back up the data.  You can take incremental backups of EBS volumes by creating Amazon EBS snapshots
  - **Amazon EBS Snapshots** are incremental backups.  This means that the first backup taken of a volume copies all the data.  For subsequence backups, only the blocks of data that have changed since the most recent snapshot are saved.
    - Incremental backups are different from full backups, in which all the data in a storage volume copies each time a backup occurs.  The full backup includes data that has not changed since the most recent backup

## Amazon Simple Storage Service (Amazon S3)

- Amazon S3 is a data store that allows you to store and retrieve an unlimited amount of data at any scale.
- Provides **object-level storage**
- Data is stored as **Objects** and put inside of **Buckets**
  - An Object is like a file and a Bucket is like a directory
- Has a max Object upload size of 5 TB
- Has Object versioning to protect from accidental deletion of an Object
- Can create permissions on who can access your Buckets and Objects
- **Objects** consist of *data*, *metadata*, and a *key*
- Recall that when you modify a file in block storage, only the pieces that are changed are updated. When a file in object storage is modified, the *entire object* is updated.
- Web enabled
- Regionally distributed
- Has 11 9's of durability
- Offers cost savings
- Serverless

### EBS Vs. S3

- **S3**:
  - Web Enabled
  - Regionally Distributed
  - 11 9's of durability
  - Offers cost savings
  - Serverless
- **EBS**
  - Micro-edits on videos and other data
  - Complex read/write/update functions

## Amazon Elastic File System (Amazon EFS)

- In **file storage**, multiple clients(users, applications, servers, ...) can access data that is stored in shared file folders.  In this approach, a storage server uses block storage with a local file system to organize files.  Clients access data through file paths.
- Compared to **block storage** or **object storage**, file storage is ideal for use cases in which a large number of services or resources need access to the same data at the same time
- **Amazon EFS** is a scalable file system used with AWS Cloud services and on-premises resources.  As you add or remove files, EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications

## Comparing EBS and EFS

- An Amazon EBS volume stores data in a **single Availability Zone**
  - To attach an Amazon EC2 instance to an EBS volume, both the Amazon EC2 instance and the EBS volume must reside in the same AZ
- Amazon EFS is a regional service.  It stores data in and across **multiple Availability Zones**
  - The duplicate storage enables you to access data concurrently from all the AZ's in a region where a file system is located.
  - Additionally, on-premises servers can access **Amazon EFS** using **AWS Direct Connect**

## Additional Resources

- [Instance Stores](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)
- [Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs)