

## **EC2** - Elastic compute cloud


Amazon **EC2** is a cloud service providing scalable computing power. 
- Users can create virtual servers called "instances" using pre-made templates known as Amazon Machine Images (AMIs). 
- AMIs contain necessary info like the operating system. 
- EC2 supports various operating systems including Amazon Linux, Ubuntu, Windows Server, MacOS, and more.

- EC2 compute units (ECUs) provide a relative measure of the integer processing power of an Amazon EC2 instance. 
- Users have complete control over the operating system layer, with root or admin access.


# **Key pairs**
- Securely connecting to EC2 instances involves using key pairs, consisting of a public key stored by AWS and a private key file stored by the user. 
**→ Protocol Port 3389**
- For Windows AMIs, the private key file is necessary to retrieve the login password, while for Linux AMIs, it facilitates secure SSH access.
**→ Port 22**

## **Metadata and User Data play essential roles:**
- Instance information can be fetched using metadata, managed by aws metadata server.

- The Instance Metadata Query tool is available to simplify querying instance metadata. This tool enables users to retrieve instance metadata without manually entering the complete URI or category names.


# **Userdata** 
- User data, presented as a script during instance launch, is limited to 16KB and is unencrypted.
- User data for instances can be accessed at http://169.254.169.254/latest/user-data/
- User-data to configure nginx server ,below
```
   #!/bin/bash 
   sudo apt-get update -y
   sudo apt install nginx  -y
   sudo systemctl enable nginx --now
   echo "<h1>Hello</h1>" >  /var/www/html/index.html
```

- Userdata server is AWS managed server that stores the userdata of your instance. 
- Everytime instance boot it contact user data server to initiate a script ( set of commands) as you defined -> cloud-init ( a kind of service) 

- You can see system logs when a system starts.  

- Userdata script will run everytime instance boot 

- With userdata we can use many language (python, perl, shell) 

- If a problem persist while running userdata, we can see logs of sloud-init stored at /var/log/cloud-init-output.log 

- If we modity the userdata after stopping the instance, It won't get updated. 

- Init and others are the  modules that fetch and run the user data 

- Clean module clean the userdata and update userdata as we modified. 





# **Installing httpd in AWS EC2**

 
```
#!/bin/bash 

$ sudo yum update  -y 

$ sudo yum install httpd -y 

$ sudo systemctl enable httpd --now 

$ sudo -i 

$ IP=$(curl http://169.254.169.254/latest/meta-data/public-ipv4) 

$ echo  "Public IP is $IP " > /var/www/html/index.html 
```


# **EC2 Instance Types**
- EC2 Instance Types offer a diverse range of options tailored to meet different use cases within the Amazon EC2 ecosystem.

- These instance types are characterized by unique combinations of CPU, memory, storage, and networking capabilities. 
- They grant users the flexibility to select an optimal blend of resources that aligns with the specific needs of their applications.

Furthermore, each instance type encompasses multiple sizes, providing the ability to scale resources according to the demands of the intended workload. This scalability allows users to fine-tune their resource allocation for optimal performance and efficiency.

Follow - [Official Documents](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html).



_________________________________________________________________


# **Steps to launch EC2 instance**


- Start by picking an **Amazon Machine Image (AMI)** for your EC2 instance.
- Decide if you want to automatically give your instance a public  IP address. The default setting follows the subnet configuration.
- Optionally, include the instance in a placement group if you have specific requirements.
- Give your instances access to AWS resources by assigning them **IAM roles**, which are like credentials.
- Prevent accidental instance termination by enabling termination protection.
- Basic monitoring is on by default. You can upgrade to detailed monitoring **(costs extra)** for more frequent updates.
- Choose between shared or dedicated tenancy based on your needs.
- **T2** unlimited lets your applications go beyond basic CPU performance when needed (extra cost).
- Add a startup script **(user data)** to customize your instance.
- For Windows instances, connect to a directory or enable an Elastic GPU if necessary.
- Explore storage options, like extra volumes, different volume types, and encryption choices.
- Use **Amazon Elastic File System (EFS)** to share files among multiple EC2 instances.
- Encrypt non-root volumes and choose encryption for root volumes when launching if you want.
- Create tags during instance setup or later to organize your instances.
- Choose existing or create new **security groups** to control instance access.
- Generate or use an existing key pair for **SSH** access. Alternatively, use the 'AmazonEC2RoleforSSM' IAM role for connection via Systems Manager (Session Manager).


------------------------------------------------------------

# **Amazon Machine Images**
An Amazon Machine Image (AMI) provides the information required to launch an instance.

An Amazon Machine Image (AMI) consists of the following components:

**Root Volume Template:**
- A blueprint for the main storage of the instance (e.g., an operating system, application server, and applications).
**Launch Permissions:**
- Controls which AWS accounts have the authority to use the AMI for launching instances.
**Block Device Mapping:**
- Specifies the volumes to attach to the instance when it is initiated.

# **Billing and provisioning**

**On-Demand:**

- Pay for usage hours without commitments.
- Flexible, low-cost, and no upfront fees.
- Ideal for auto-scaling groups and unpredictable workloads.
- Well-suited for development and testing.

**Spot:**
- Utilizes unused EC2 capacity in AWS.
- Offers up to a 90% discount compared to On-Demand prices.
- Suitable for various stateless, fault-tolerant, or flexible applications.
- Requested through the Spot management console, CLI, API, or the same interface as On-Demand instances.
- Allows customization with Launch Templates, security configurations, multiple instance types, locations, static IP endpoints, and persistent block storage.


# **Dedicated Hosts:**

- Get your physical servers.
- You choose which instances go on the server.
- Can be On-Demand or reserved.
- Useful for certain software licenses.
- Each host runs just one type of EC2 instance.
- Good for rules or licenses.
- You know what performance to expect.
- It's the priciest option, and you pay per host.

# **Dedicated Instances:**

- Virtual instances on special hardware.
- Uses dedicated EC2 servers.
- Less control than dedicated hosts.
- Pay for each instance.
- May share hardware with regular instances.
- Available On-Demand, Reserved, or as Spot Instances.
- Costs $2 extra per hour per region.


``
Instances are billed when they’re running – need to stop or terminate to avoid paying.
Charges are incurred by the hour or second for Linux instances.
Data transfer between instances in different regions is billable for both inbound and outbound traffic.
``

# **Network**

**IP Addresses:**

- Public Address: Automatically assigned to instances in public subnets; changes if the instance is stopped/started.
- Private Address: Automatically assigned to all instances.
- Elastic IP: Static public address.

**Address Retention:**

- Public IPv4 addresses are lost when the instance is stopped, but private addresses (both IPv4 and IPv6) are kept.
- Public IPv4 addresses are retained when the instance is restarted.


## **Elastic IP Address:**

- Elastic IPs are preserved even when the instance is in a stopped state.
- These IPs are static and can be reassigned (moved) between instances.
- Each account starts with a default limit of 5 Elastic IPs per region, but this limit can be increased through AWS Support.
- AWS charges for Elastic IPs that are not actively in use.
- Elastic IPs are specific to a particular region.
- Custom tags can be assigned to categorize Elastic IP addresses.



**Exam Tip:**
- If you encounter issues with EC2 status checks or there's scheduled maintenance on the current physical host, consider stopping and starting the EC2 instance. 
- This action can help relocate the instance to a different physical host, resolving potential problems.



`` 
When an instance is stopped, you can modify the following attributes:
``

**Instance Type:** You can change the type of the instance during the stopped state.

**User Data:** Modifications to the user data associated with the instance can be made.

**Kernel:** The kernel, or the core component of the operating system, can be modified.

**RAM Disk:** Changes to the RAM disk associated with the instance are allowed.


---------------------------------------------------

# **Elastic Network Interfaces (ENIs)**
``
Elastic Network Interfaces (ENIs) are logical networking components within a VPC, serving as virtual network cards. 
``

These interfaces possess the following attributes:

- **Primary Private IPv4 Address**: Derived from the VPC's IPv4 address range.
- **Secondary Private IPv4 Addresses**: Additional IPv4 addresses from the VPC's range.
- **Elastic IP Address (IPv4)**: One per private IPv4 address for external access.
- **Public IPv4 Address**: Available if required.
- **IPv6 Addresses**: Support for IPv6 connectivity.
- **Security Groups**: Controls for inbound and outbound traffic.
- **MAC Address**: Unique identifier for network communication.
- **Source/Destination Check Flag**: Ensures packets are routed correctly.
- **Description**: Customizable label for identification purposes.


# **Attaching ENIs:**
- ENIs can be “hot attached” to running instances.
- ENIs can be “warm-attached” when the instance is stopped.
- ENIs can be “cold-attached” when the instance is launched.



# **IAM Roles**
``
IAM Roles are a safer alternative to storing access keys directly on EC2 instances.
``

### **Points to note:**

- IAM roles allow EC2 instances to securely interact with various services like S3 and DynamoDB.
- They are easier to manage and more secure than traditional access keys.
- You can attach IAM roles during the instance launch or later using AWS CLI, SDK, or the EC2 console.
- Roles can be attached, changed, or replaced whenever needed, providing flexibility.
- Each EC2 instance can have only one IAM role at a time.
- IAM roles work universally, across all AWS regions.



# **Bastion/Jump Hosts:**
- Set up EC2 instances as bastion hosts (jump boxes) for managing VPC instances.
- Connect to the bastion host using SSH or RDP protocols.
- Configure a security group with the necessary permissions.
- Choose between auto-assigned public IPs or Elastic IPs.
- Use security groups to limit access to the bastion host based on specific IP addresses or CIDRs.
- For high availability, use auto-scaling groups (with 1 instance for replacement if needed).
- It's a good practice to deploy Linux bastion hosts in two Availability Zones, with auto-scaling and Elastic IP addresses.
- Alternatively, AWS Systems Manager Session Manager can be used instead of bastion hosts.


## **Keeping an Eye on Your EC2 Instances:**


# **Monitoring** 
- EC2 keeps a close watch on your instance every minute to make sure things are running smoothly.
- If everything is good, your instance is given a thumbs up; if not, it's marked as having a problem.
- Major issues, like network or power troubles, are taken care of by AWS itself.
- For smaller problems, such as running out of memory, you need to step in and fix them.
- These checks are an integral part of EC2 and can't be turned off.
- You can set up alerts using Amazon CloudWatch based on these checks.
- CloudWatch can automatically take actions like restarting your instance if it's not performing well.
- It's recommended to let EC2 handle the restart instead of doing it through the operating system.
- CloudWatch checks your instance either every 5 minutes (standard check) or every 1 minute (advanced check, which comes with a small extra cost).





























