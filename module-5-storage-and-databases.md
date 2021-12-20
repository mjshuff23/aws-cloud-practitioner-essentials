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
- You can think of block-level storage as a place to store files. A file being a series of bytes that are stored in blocks on disc. When a file is updated, the whole series of blocks aren't all overwritten. Instead, it updates just the pieces that change. This makes it an efficient storage type when working with applications like databases, enterprise software, or file systems.
- When you launch an EC2 instance, depending on the type of the EC2 instance you launched, it might provide you with local storage called instance store volumes. These volumes are physically attached to the host, your EC2 instances running on top of. And you can write to it just like a normal hard drive. The catch here is that since this volume is attached to the underlying physical host, if you stop or terminate your EC2 instance, all data written to the instance store volume will be deleted. 

### Instance Stores

Block-level storage volumes behave like physical hard drives

- An **instance store** provides temporary block-level storage for an Amazon EC2 instance.  An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance.  When the instance is terminated, you lose any data in the instance store.

- **Amazon Elastic Block Store (Amazon EBS)** is a service that provides block-level storage volumes that you can use with EC2 instances.  If an EC2 instance is stopped or terminated, data will persist on an EBS volume.
  - To create an EBS volume, you define the configuration (such as volume size and type) and provision it.  After you create an EBS volume, it can attach to an EC2 instance
  - Because EBS volumes are for data that needs to persist, it's important to back up the data.  You can take incremental backups of EBS volumes by creating Amazon EBS snapshots
  - **Amazon EBS Snapshots** are incremental backups.  This means that the first backup taken of a volume copies all the data.  For subsequence backups, only the blocks of data that have changed since the most recent snapshot are saved.
    - Incremental backups are different from full backups, in which all the data in a storage volume copies each time a backup occurs.  The full backup includes data that has not changed since the most recent backup

## Additional Resources

- [Instance Stores](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)
- [Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs)