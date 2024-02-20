![alt text](https://digitalcloud.training/wp-content/uploads/2022/01/Amazon-EFS.jpg)

# Elastic File System (EFS) - Simplifying File Storage in AWS

As users, we often prefer not to manage disk volumes but use them to store files. AWS simplifies this by managing file systems for EFS.


## Overview

- Amazon EFS provides a simple, serverless, set-and-forget elastic file system.
- Create a file system, mount it on an Amazon EC2 instance, and read and write data to and from your file system.
- Mount the Amazon EFS file system in your virtual private cloud (VPC) through the Network File System versions 4.0 and 4.1 (NFSv4) protocol.
- Recommended Linux NFSv4.1 clients: latest Amazon Linux, Amazon Linux 2, Red Hat, Ubuntu, and macOS Big Sur AMIs.
- Access your Amazon EFS file system concurrently from multiple NFS clients.
- AWS compute instances in multiple Availability Zones within the same AWS Region can access the file system.



------------------------------------------
------------------------------------------

## Supported Regions and Protocols

- For a list of AWS Regions where you can create an Amazon EFS file system, see the Amazon Web Services General Reference.
- Create one or more mount targets in the VPC to access your Amazon EFS file system.

## Mount Targets

- For Regional file systems, create a mount target in each Availability Zone in the AWS Region.
- For One Zone file systems, create a single mount target in the same Availability Zone as the file system.
- For more information, see EFS storage classes.

--------------------------------------
---------------------------------------

## EFS (Elastic File System)

EFS is a scalable and flexible Network Attached Storage (NAS) solution in AWS.

- **Flexibility:** Pay only for the storage you use; no need to manage fixed-sized disks.
- **Scalability:** NAS servers, known as File Servers, are scalable, allowing you to add storage as needed.
- **Availability and Durability:** Data can be replicated over multiple Availability Zones (AZs), providing both availability and durability.
- **Replication:** Built-in replication ensures data availability in case of failures.

-----------------------------------
-------------------------------------------
## Lifecycle Management

EFS offers Lifecycle Management to optimize costs based on file usage patterns.

- **High IOPS and Throughput:** For frequently accessed files.
- **Lower IOPS and Throughput:** For less frequently used files.
------------------------------------------

## Use Case

When you have multiple webservers running on EC2 instances that need access to the same data, EFS is an excellent choice.


- After mounting the file system, use it like any other POSIX-compliant file system.
- For NFS-level permissions and related considerations, see Working with users, groups, and permissions at the Network File System (NFS) Level.

------------------------------

- **Example:** Provision EFS and mount it on multiple webservers running on EC2 instances, ensuring consistent data across instances.

## Note

EFS is compatible only with Linux.

----------------------------------------------------
------------------------------------------
----------------------------------------
--------------------------------------------

## Mount Target Details

- A mount target provides an IP address for an NFSv4 endpoint to mount an Amazon EFS file system.
- Mount the file system using its Domain Name Service (DNS) name.
- DNS resolves to the IP address of the EFS mount target in the same Availability Zone as your EC2 instance.
- Design considerations for high availability and failover to other Availability Zones.


--------------------------
--------------------------------
-------------------------
-----------------------------


# How Amazon EFS Works with Amazon EC2

This section explains how Amazon EFS Regional and One Zone file systems are mounted to EC2 instances in an Amazon VPC.

## Amazon EFS Regional File Systems

The illustration below shows multiple EC2 instances accessing an Amazon EFS file system configured for multiple Availability Zones in an AWS Region.



<img src="https://docs.aws.amazon.com/images/efs/latest/ug/images/efs-ec2-how-it-works-Regional_china-world.png" alt="S3" width="400"/>

In this illustration:
- The virtual private cloud (VPC) has three Availability Zones.
- The Regional file system has a mount target in each Availability Zone.
- We recommend accessing the file system from a mount target within the same Availability Zone for performance and cost reasons.
- One of the Availability Zones has two subnets, but a mount target is created in only one of the subnets.



## Amazon EFS One Zone File Systems

The illustration below shows multiple EC2 instances accessing a One Zone file system from different Availability Zones in a single AWS Region.



<img src="https://docs.aws.amazon.com/images/efs/latest/ug/images/efs-ec2-how-it-works-OneZone.png" alt="S3" width="400"/>

In this illustration:
- The VPC has two Availability Zones, each with one subnet.
- One Zone file systems can only have a single mount target.
- For better performance and cost, we recommend accessing the file system from a mount target in the same Availability Zone as the EC2 instance.

In this example, the EC2 instance in the us-west-2c Availability Zone will pay EC2 data access charges for accessing a mount target in a different Availability Zone.



-------------------------
--------------------------
----------------------

# Authentication and Access Control

- To make Amazon EFS API requests, such as creating a file system, you must have valid credentials. Additionally, you need the necessary permissions to create or access resources.

## AWS Identity and Access Management (IAM)

- Users and roles created in AWS IAM must be granted the appropriate permissions for resource creation or access. For detailed information about permissions, refer to the [Identity and Access Management for Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/security-iam.html).

## IAM Authorization for NFS Clients

- IAM authorization for NFS clients is an additional security option for Amazon EFS. It leverages IAM to simplify access management for Network File System (NFS) clients at scale. This approach allows you to use IAM for managing access to an EFS file system in a scalable manner, optimized for cloud environments.

- For detailed instructions on using IAM authorization for NFS clients, refer to [Using IAM to Control File System Data Access](https://docs.aws.amazon.com/efs/latest/ug/iam-access-control-nfs-efs.html).

------------------------
-------------------------------
------------------

# EFS Replication

- Create a replica of your Amazon EFS file system in the AWS Region of your preference using replication.

- Replication automatically and transparently replicates the data and metadata on your EFS file system to a new destination EFS file system created in an AWS Region of your choice.

- EFS ensures that the source and destination file systems stay synchronized continuously through automatic replication.

- Replication is designed to provide a low Recovery Point Objective (RPO) and a quick Recovery Time Objective (RTO), both in the order of minutes.

- These features are crucial for meeting compliance and business continuity goals.

- For more detailed information, refer to the [Replicating File Systems](https://docs.aws.amazon.com/efs/latest/ug/efs-replication.htmls) documentation.


-------------------------------
--------------------
----------------------






