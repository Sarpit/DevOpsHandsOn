
## Question 1:
**What is Amazon EC2 used for in AWS?**

**Options:**
1. Data storage
2. Compute capacity
3. DNS management
4. Content delivery

<details>
<summary><strong>Answer:</strong> 2. Compute capacity</summary>

<strong>Explanation:</strong> Amazon EC2 provides resizable compute capacity in the cloud, allowing users to run virtual servers.
</details>

---

## Question 2:
**Which of the following is a valid EC2 instance type?**

**Options:**
1. Pico
2. Giga
3. Nano
4. Mega

<details>
<summary><strong>Answer:</strong> 3. Nano</summary>

<strong>Explanation:</strong> EC2 instance types include Nano, Micro, Small, Medium, Large, X-Large, among others.
</details>

---

## Question 3:
**What is an AMI in the context of EC2?**

**Options:**
1. Amazon Machine Image
2. Advanced Memory Instance
3. Automated Migration Interface
4. Application Management Interface

<details>
<summary><strong>Answer:</strong> 1. Amazon Machine Image</summary>

<strong>Explanation:</strong> An Amazon Machine Image (AMI) is a pre-configured virtual machine image, which is used to create EC2 instances.
</details>

---

## Question 4:
**Which EC2 feature allows you to balance incoming traffic across multiple instances?**

**Options:**
1. Amazon S3
2. Elastic Load Balancer (ELB)
3. Auto Scaling
4. Route 53

<details>
<summary><strong>Answer:</strong> 2. Elastic Load Balancer (ELB)</summary>

<strong>Explanation:</strong> ELB automatically distributes incoming application traffic across multiple targets, such as EC2 instances.
</details>

---

## Question 5:
**What is the purpose of EC2 security groups?**

**Options:**
1. Manage billing information
2. Configure auto-scaling policies
3. Define firewall rules
4. Create virtual private networks

<details>
<summary><strong>Answer:</strong> 3. Define firewall rules</summary>

<strong>Explanation:</strong> EC2 security groups act as virtual firewalls, controlling inbound and outbound traffic to EC2 instances.
</details>

---

## Question 6:
**Which storage option is suitable for EC2 instances requiring low-latency access to data?**

**Options:**
1. Amazon S3
2. Amazon EBS
3. Amazon Glacier
4. Amazon RDS

<details>
<summary><strong>Answer:</strong> 2. Amazon EBS</summary>

<strong>Explanation:</strong> Amazon Elastic Block Store (EBS) provides block-level storage volumes for EC2 instances, suitable for low-latency access.
</details>

---

## Question 7:
**What is an EC2 instance type designed for memory-intensive applications?**

**Options:**
1. T2
2. M5
3. C5
4. R5

<details>
<summary><strong>Answer:</strong> 4. R5</summary>

<strong>Explanation:</strong> R5 instances are designed for memory-intensive applications, providing high memory-to-vCPU ratios.
</details>

---

## Question 8:
**Which service helps you automatically scale the number of EC2 instances based on demand?**

**Options:**
1. Amazon S3
2. Amazon EC2 Auto Scaling
3. AWS Lambda
4. Amazon RDS

<details>
<summary><strong>Answer:</strong> 2. Amazon EC2 Auto Scaling</summary>

<strong>Explanation:</strong> EC2 Auto Scaling allows you to automatically adjust the number of EC2 instances based on defined policies.
</details>

---

## Question 9:
**What is the purpose of an EC2 Key Pair?**

**Options:**
1. Authorize access to S3 buckets
2. Establish secure communication between instances
3. Authenticate users in IAM
4. Securely connect to EC2 instances

<details>
<summary><strong>Answer:</strong> 4. Securely connect to EC2 instances</summary>

<strong>Explanation:</strong> EC2 Key Pairs are used to securely SSH into EC2 instances, providing a secure method for authentication.
</details>

---

## Question 10:
**Which AWS service allows you to monitor and collect data about your EC2 instances?**

**Options:**
1. AWS CloudTrail
2. Amazon CloudWatch
3. Amazon Inspector
4. AWS Config

<details>
<summary><strong>Answer:</strong> 2. Amazon CloudWatch</summary>

<strong>Explanation:</strong> CloudWatch is a monitoring service that allows you to collect and track metrics, collect log files, and set alarms for EC2 instances.
</details>


## Question 11:
**Scenario:**
You are tasked with deploying a web application that requires high availability. Which EC2 feature should you use to ensure the application can handle varying levels of traffic by automatically adjusting the number of instances?

**Options:**
1. Elastic Load Balancer (ELB)
2. EC2 Auto Scaling
3. Amazon RDS
4. EC2 Security Groups

<details>
<summary><strong>Answer:</strong> 2. EC2 Auto Scaling</summary>

<strong>Explanation:</strong> EC2 Auto Scaling allows you to automatically adjust the number of EC2 instances based on defined policies, ensuring high availability.
</details>

---

## Question 12:
**Scenario:**
You need to deploy an application that requires low-latency access to a large dataset. Which EC2 storage option is most suitable for this scenario?

**Options:**
1. Amazon S3
2. Amazon EBS
3. Amazon RDS
4. Instance Store

<details>
<summary><strong>Answer:</strong> 2. Amazon EBS</summary>

<strong>Explanation:</strong> Amazon Elastic Block Store (EBS) provides block-level storage volumes for EC2 instances, suitable for low-latency access.
</details>

---------------------------------------

## Question 13:
**Scenario:**
You are running a memory-intensive application on EC2 instances. Which EC2 instance type should you choose for optimal performance?

**Options:**
1. T3
2. M5
3. C5
4. R5

<details>
<summary><strong>Answer:</strong> 4. R5</summary>

<strong>Explanation:</strong> R5 instances are...
----------------------------------------

## Question 14:
**Scenario:**
Your application involves handling traffic spikes during specific hours of the day. Which service helps you automatically scale the number of EC2 instances based on demand?

**Options:**
1. Amazon S3
2. AWS Lambda
3. Amazon EC2 Auto Scaling
4. AWS Elastic Beanstalk

<details>
<summary><strong>Answer:</strong> 3. Amazon EC2 Auto Scaling</summary>

<strong>Explanation:</strong> EC2 Auto Scaling automatically adjusts the number of EC2 instances based on defined policies, making it suitable for handling traffic spikes.
</details>

---

## Question 15:
**Scenario:**
You want to ensure that your EC2 instances are securely accessed over SSH. What AWS resource would you use for secure authentication?

**Options:**
1. IAM Roles
2. EC2 Key Pairs
3. Security Groups
4. Multi-Factor Authentication (MFA)

<details>
<summary><strong>Answer:</strong> 2. EC2 Key Pairs</summary>

<strong>Explanation:</strong> EC2 Key Pairs are used for securely connecting to EC2 instances over SSH, providing a secure method for authentication.
</details>

---

## Question 16:
**Scenario:**
Your organization is hosting a critical web application. Which AWS service allows you to distribute incoming traffic across multiple EC2 instances for improved availability?

**Options:**
1. Amazon Route 53
2. Elastic Load Balancer (ELB)
3. AWS CloudFront
4. Amazon API Gateway
[O
<details>
<summary><strong>Answer:</strong> 2. Elastic Load Balancer (ELB)</summary>

<strong>Explanation:</strong> ELB automatically distributes incoming application traffic across multiple EC2 instances for improved availability.
</details>

---

## Question 17:
**Scenario:**
You need to monitor the performance and health of your EC2 instances. What AWS service provides monitoring, logging, and alarming capabilities for EC2?

**Options:**
1. Amazon CloudWatch
2. AWS CloudTrail
3. Amazon Inspector
4. AWS Config

<details>
<summary><strong>Answer:</strong> 1. Amazon CloudWatch</summary>

<strong>Explanation:</strong> CloudWatch is a monitoring service that provides metrics, logs, and alarms for EC2 instances.
</details>

---

## Question 18:
**Scenario:**
Your application requires persistent block-level storage that can be detached and reattached to different EC2 instances. What AWS storage service meets this requirement?

**Options:**
1. Amazon S3
2. Amazon EFS
3. Amazon RDS
4. Amazon EBS

<details>
<summary><strong>Answer:</strong> 4. Amazon EBS</summary>

<strong>Explanation:</strong> Amazon Elastic Block Store (EBS) provides block-level storage volumes that can be detached and reattached to different EC2 instances.
</details>

---

## Question 19:
**Scenario:**
You want to control inbound and outbound traffic to your EC2 instances. What AWS resource enables you to define firewall rules for EC2 instances?

**Options:**
1. IAM Policies
2. Amazon VPC
3. EC2 Security Groups
4. Amazon Inspector

<details>
<summary><strong>Answer:</strong> 3. EC2 Security Groups</summary>

<strong>Explanation:</strong> EC2 Security Groups act as virtual firewalls, controlling inbound and outbound traffic to EC2 instances.
</details>

---

## Question 20:
**Scenario:**
You need to deploy a web application with a custom domain. Which AWS service allows you to route traffic to different EC2 instances based on the domain name?

**Options:**
1. Amazon Route 53
2. Elastic Load Balancer (ELB)
3. AWS CloudFront
4. Amazon API Gateway

<details>
<summary><strong>Answer:</strong> 1. Amazon Route 53</summary>

<strong>Explanation:</strong> Amazon Route 53 is a scalable domain name system (DNS) web service that allows you to route traffic to different AWS resources, including EC2 instances, based on the domain name.
</details>

