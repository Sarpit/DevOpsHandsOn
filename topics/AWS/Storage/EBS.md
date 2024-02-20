![alt text](https://digitalcloud.training/wp-content/uploads/2022/01/Amazon-EBS.jpg)

 
# <span style="color:Yellow">**Amazon Elastic Block Store (Amazon EBS)**</span>


- **Functionality**: EBS provides block-level storage volumes for use with EC2 instances.

- **Behaviour**: EBS volumes act like raw, unformatted block devices that can be mounted on EC2 instances.

- **Persistence**: Volumes persist independently of the instance's lifecycle.

- **Configuration**: You can dynamically change the configuration of a volume attached to an instance.

- **Recommendation**: EBS is suggested for data requiring quick access and long-term persistence.

- **Use Cases**: Well-suited for primary storage in file systems, databases, and applications needing fine-grained updates and access to raw block-level storage.

- **Flexibility**: Can create a file system on the volumes or use them as block devices like hard drives.

- **Applications**: Suitable for database-style applications with random reads/writes and throughput-intensive applications with continuous reads/writes.


# <span style="color:pink">**Features of EBS** </span>
- **Availability Zone Specific**: EBS volumes are created and attached to instances in a specific Availability Zone.

- **Snapshot and Restore**: You can make volumes available outside the Availability Zone by creating a snapshot and restoring it to a new volume in the same Region or a different Region.

- **Geographical Expansion and Disaster Recovery**: Snapshots can be copied to other Regions for geographical expansion, data center migration, and disaster recovery.

------------------------------
## <span style="color:Pink">**Volume Types:** </span>

- **General Purpose SSD (gp2 and gp3)**: Balances price and performance for various workloads like boot volumes, medium-sized databases, and development environments.

- **Provisioned IOPS SSD (io1 and io2)**: Designed for I/O-intensive workloads, providing a consistent IOPS rate and high durability.

- **Throughput Optimized HDD (st1)**: Low-cost magnetic storage ideal for large, sequential workloads like data warehouses and log processing.

- **Cold HDD (sc1)**: Low-cost magnetic storage for large, infrequently accessed, sequential data.

----------------------------------------------------

----------------------------------------------------
- **Encryption:** EBS volumes can be created as encrypted, ensuring data-at-rest encryption for regulated/audited data. Encryption covers data on the volume, disk I/O, and snapshots.

- **Snapshots**: Point-in-time snapshots of EBS volumes are stored in Amazon S3, providing long-term data durability. Snapshots can be used as starting points for new volumes and copied across AWS Regions.

- **Performance Monitoring**: Performance metrics such as bandwidth, throughput, latency, and average queue length are available through the AWS Management Console via Amazon CloudWatch. This allows monitoring and optimization of volume performance without unnecessary resource costs.

--------------------------------------------------------

--------------------------------------------------------


# <span style="color:cyan">**Amazon EBS Volume Overview in Simple Terms**</span>
![alt text](https://i.ytimg.com/vi/Dy4Ob3Lw8ik/maxresdefault.jpg)


- **Definition**: An Amazon EBS volume is like a digital, durable hard drive that you can attach to your virtual server (instance) in the cloud.

- **Functionality**: Once attached, it behaves just like a physical hard drive, allowing you to use it for various purposes, such as storing data or running a database.

- **Flexibility**: You can easily adjust the size, change performance settings, and even switch the type of the volume while it's actively being used.

- **Use Cases**: Useful for storing frequently updated data (like an operating system drive) or for applications needing continuous disk scans.

- **Persistence**: EBS volumes persist independently of the virtual server's lifecycle. They don't vanish if the server is stopped or restarted.

- **Multi-Attach**: You can connect multiple EBS volumes to a single server, enhancing storage capabilities. However, both the volume and server must be in the same location.

----------------------------------------------------------


### <span style="color:pink">Volume Types:</span>

    General Purpose SSD (gp2 and gp3): Balances performance and cost for various workloads.

    Provisioned IOPS SSD (io1 and io2): Tailored for workloads requiring high I/O performance.

    Throughput Optimized HDD (st1): Ideal for applications with continuous disk scans.

    Cold HDD (sc1): Cost-effective storage for infrequently accessed data.

    Magnetic (standard): Basic storage option with balanced performance.

----------------------------------------------------
- **Limits**: Be aware of your account's storage limits, and if needed, you can request an increase in these limits.
-------------------------------------------------


# <span style="color: cyan">Benefits of Using Amazon EBS Volumes</span>

### Data Availability:

- Automatically safeguards data within its Availability Zone, preventing loss from hardware issues.
- Easily attachable to any EC2 instance in the same Availability Zone, presenting as a native block device.

### Data Persistence:

- Volumes persist independently of the instance's lifespan, ensuring data survival even if the instance is terminated.
- Volumes can be detached with data intact, ready for quick recovery when attached to a new instance.

### Data Encryption:

- Simple encryption with 256-bit AES algorithms for enhanced security.
- Leverages AWS Key Management Service (AWS KMS) master keys, adding an extra layer of protection.

### Data Security:

- Presented as raw, unformatted block devices, ensuring logical emptiness before user interaction.
- Allows users to follow specific data erasure procedures, complying with security manuals.

### Snapshots:

- Enables effortless creation of snapshots (backups) redundantly stored in multiple Availability Zones on Amazon S3.
- Snapshots are versatile, facilitating the creation of new volumes or moving volumes across Availability Zones, with incremental updates for cost efficiency.

### Flexibility:

- Supports live configuration changes during production, adapting to evolving needs.
- Enables hassle-free modification of volume type, size, and IOPS capacity without service interruptions using Amazon EBS Elastic Volumes.

*Enhance your data management with Amazon EBS - a flexible and secure solution for your cloud storage needs.*

--------------


------------------------------------
--------------------------



# <span style="color: cyan">**Amazon EBS Service Limitations Simplified**</span>

### Virtual Drives:

Amazon EBS makes cloud storage work like virtual hard drives for EC2 instances.

### Operating System Handling:

Your computer (operating system) thinks EBS drives are regular hard drives, managing data on them like it would on any disk.

### Data Awareness:

EBS doesn't know what's on the drives; it just makes sure the parts are intact. Actions by AWS and your computer are independent.

### Volume Size Limit:

EBS can create drives up to 64 Terabytes in size, but your computer's ability to use all of it depends on how it's set up.

### Linux Booting:

For Linux systems, how much data your startup drive can hold depends on the setup. It's like deciding if a room can fit a certain size of furniture.

### AMI Influence:

The kind of setup (MBR or GPT) your computer uses is influenced by the initial instructions from the Amazon Machine Image (AMI) when you start your virtual machine.

### Considerations for Linux AMIs:

For Linux, the rules about drive sizes depend on how your AMI (like a setup manual) says the computer should handle drives.

### *Practical Advice:*

*Check how big your drives can be based on your AMI, and make sure your computer's setup matches what you need.*

-----------

## <span style="color: cyan">*Encryption*</span>

### **Encrypted EBS Volumes:**
  - Keeps your data safe when resting or moving between your computer and the storage.
  - Backups and their new copies are automatically secured.

### **Encrypting an Unsecured Volume:**
  1. Take a picture of your data.
  2. Make a safe copy of that picture.
  3. Create a new storage from the safe copy.

### **Note:**
  - Some computers may not support this security feature.

## <span style="color: cyan">Snapshots</span>

### **Using Data Lifecycle Manager (DLM):**
  - Sets up automatic picture-taking, keeping, and deleting for your storage.

### **Picture Facts:**
  - New pictures only save changes since the last one.
  - You only need the latest picture to bring back all your data.

## <span style="color: cyan">RAID (Redundant Array of Independent Disks)</span>

### RAID 0

- **Purpose:**
  - Makes your storage work faster by sharing tasks between different parts.

- **Benefits:**
  - Adding more storage makes things run even faster.
  
- **Use Cases:**
  - Great for programs that need to work really fast.

### RAID 1

- **Purpose:**
  - Ensures your data stays safe by keeping extra copies in different parts.
  
- **Use Cases:**
  - Perfect for programs where keeping data safe is super important.


## <span style="color: cyan">Additional Resources:</span>

- [Creating Amazon EBS Volumes](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-volume.html)
- [Attaching Amazon EBS Volumes to EC2 Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-attaching-volume.html)

------------------------


