# **Scenario-1:**
ABC Corporation is a multinational company specializing in e-commerce solutions. They operate an extensive online marketplace that connects buyers and sellers globally. The company experiences varying levels of website traffic throughout the day due to different time zones and promotional events. During peak hours, there is a significant surge in user activity, leading to increased demands on their e-commerce platform. To ensure a seamless and responsive user experience, ABC Corporation has decided to leverage cloud services and is considering AWS as their cloud provider.

They plan to deploy their e-commerce application on AWS EC2 instances. The application consists of a web server handling user requests, a database server managing product catalogs and transactions, and additional application servers for background tasks such as order processing and inventory management. ABC Corporation aims to optimize costs while ensuring high availability and scalability to accommodate traffic spikes.

## **Question-1:**
Considering the e-commerce scenario described for ABC Corporation, which EC2 feature or service would be most appropriate to ensure optimal cost management during non-peak hours while providing the ability to scale during peak traffic?

**Options:**
1. EC2 Reserved Instances
2. EC2 Spot Instances
3. EC2 Auto Scaling
4. EC2 Dedicated Hosts

<details>
<summary><strong>Answer:</strong> 3. EC2 Auto Scaling</summary>

<strong>Explanation:</strong> EC2 Auto Scaling allows ABC Corporation to automatically adjust the number of EC2 instances based on traffic demand. This ensures optimal cost management during non-peak hours by scaling down instances when the demand is low and scaling up during peak traffic to handle increased loads. This feature aligns with ABC Corporation's goal of achieving cost efficiency while maintaining application responsiveness.
</details>


## Question 2:
### **Scenario:**
XYZ Tech Solutions is a software development company that recently migrated its applications to the AWS cloud. They have a distributed architecture with multiple microservices running on Amazon EC2 instances. The company prioritizes security and wants to implement secure access controls and monitoring for their EC2 instances.

**Question:**
For ensuring secure access to EC2 instances in XYZ Tech Solutions, which AWS service should be used to securely store and manage SSH key pairs for EC2 instance access?

**Options:**
1. AWS Key Management Service (KMS)
2. AWS Identity and Access Management (IAM)
3. AWS Certificate Manager (ACM)
4. AWS Systems Manager (SSM)

<details>
<summary><strong>Answer:</strong> 2. AWS Identity and Access Management (IAM)</summary>

<strong>Explanation:</strong> IAM provides centralized control over AWS resources, including EC2 instances. It allows XYZ Tech Solutions to manage access to EC2 instances securely by creating and managing IAM roles, policies, and users.
</details>

---

## Question 3:
### **Scenario:**
XYZ Tech Solutions wants to monitor the performance and health of EC2 instances. For collecting and analyzing metrics, which AWS service should they use?

**Options:**
1. AWS CloudWatch
2. AWS CloudTrail
3. AWS X-Ray
4. AWS Inspector

<details>
<summary><strong>Answer:</strong> 1. AWS CloudWatch</summary>

<strong>Explanation:</strong> AWS CloudWatch is a monitoring service that allows XYZ Tech Solutions to collect and track metrics, collect and monitor log files, and set alarms. It helps in gaining insights into the performance and health of EC2 instances.
</details>

---

## Question 4:
### **Scenario:**
XYZ Tech Solutions wants to ensure data at rest on their EC2 instances is encrypted. Which EC2 feature should they use for encrypting EBS volumes attached to their instances?

**Options:**
1. EC2 Key Pairs
2. EC2 Instance Store
3. EC2 Security Groups
4. EC2 Elastic Load Balancer

<details>
<summary><strong>Answer:</strong> 1. EC2 Key Pairs</summary>

<strong>Explanation:</strong> EC2 Key Pairs are used for secure access to EC2 instances, but for encrypting data at rest on EBS volumes, XYZ Tech Solutions should use AWS Key Management Service (KMS) or other encryption mechanisms.
</details>

---

## Question 5:
### **Scenario:**
To distribute incoming application traffic across multiple EC2 instances, which AWS service should XYZ Tech Solutions use?

**Options:**
1. AWS CloudFront
2. AWS Route 53
3. AWS Elastic Load Balancer (ELB)
4. AWS API Gateway

<details>
<summary><strong>Answer:</strong> 3. AWS Elastic Load Balancer (ELB)</summary>

<strong>Explanation:</strong> ELB automatically distributes incoming application traffic across multiple EC2 instances, enhancing fault tolerance and ensuring high availability.
</details>

---

## Question 6:
### **Scenario:**
XYZ Tech Solutions wants to launch EC2 instances with a predefined set of configurations, including the AMI, instance type, and security groups. Which EC2 feature enables them to achieve this?

**Options:**
1. EC2 Reserved Instances
2. EC2 Spot Instances
3. EC2 Launch Templates
4. EC2 Auto Scaling Groups

<details>
<summary><strong>Answer:</strong> 3. EC2 Launch Templates</summary>

<strong>Explanation:</strong> EC2 Launch Templates allow XYZ Tech Solutions to specify the configurations for launching EC2 instances consistently. This includes the AMI, instance type, security groups, and other settings.
</details>

