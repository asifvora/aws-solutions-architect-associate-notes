# Aws Solutions Architect Associate Notes

> Click ⭐ if you like the project.

## Visit Document Website

https://aws-solutions-architect-associate-notes.vercel.app

### Table of Contents

| No. | Questions                                                                                               |
| --- | ------------------------------------------------------------------------------------------------------- |
|     | **AWS**                                                                                                 |
| 1   | [What is AWS?](#what-is-AWS)                                                                            |
| 2   | [AWS Cloud Use Cases](#AWS-Cloud-Use-Cases)                                                             |
| 3   | [Global Services](#Global-Services)                                                                     |
| 4   | [Region-scoped Services](#Region-scoped-Services)                                                       |
|     | **AWS IAM (AWS Identity and Access Management)**                                                        |
| 1   | [What is IAM?](#what-is-IAM)                                                                            |
| 2   | [IAM features](#IAM-features)                                                                           |
| 3   | [Accessing IAM](#Accessing-IAM)                                                                         |
| 4   | [Users & Groups](#Users-&-Groups)                                                                       |
| 5   | [Permissions](#Permissions)                                                                             |
| 6   | [Roles for Services](#Roles-for-Services)                                                               |
| 7   | [Permissions](#Permissions)                                                                             |
| 8   | [Security Tools](#Security-Tools)                                                                       |
| 9   | [Guidelines & Best Practices](#Guidelines-&-Best-Practices)                                             |
|     | **Amazon EC2 – Fundamentals**                                                                           |
| 1   | [What is Amazon EC2?](#what-is-Amazon-EC2)                                                              |
| 2   | [EC2 sizing & configuration options](#EC2-sizing-&-configuration-options)                               |
| 3   | [EC2 InstanceTypes - Overview](#EC2-InstanceTypes---Overview)                                           |
| 4   | [EC2 InstanceTypes - Example](#EC2-InstanceTypes---Example)                                             |
| 5   | [Introduction to Security Groups](#Introduction-to-Security-Groups)                                     |
| 6   | [Classic Ports](#Classic-Ports)                                                                         |
| 7   | [SSH Summary Table](#SSH-Summary-Table)                                                                 |
| 8   | [EC2 Instances Purchasing Options](#EC2-Instances-Purchasing-Options)                                   |
|     | **Amazon EC2 – Solutions Architect Associate Level**                                                    |
| 1   | [Private vs Public IP (IPv4)](<#Private-vs-Public-IP-(IPv4)>)                                           |
| 2   | [Placement groups](#Placement-groups)                                                                   |
| 3   | [Elastic Network Interfaces (ENI)](<#Elastic-Network-Interfaces-(ENI)>)                                 |
| 4   | [EC2 Hibernate](#EC2-Hibernate)                                                                         |
|     | **Amazon Amazon EC2 – Instance Storage**                                                                |
| 1   | [EBS Overview](#EBS-Overview)                                                                           |
| 2   | [EBS Snapshots](#EBS-Snapshots)                                                                         |
| 3   | [AMI Overview](#AMI-Overview)                                                                           |
| 4   | [EC2 Instance Store](#EC2-Instance-Store)                                                               |
| 5   | [EBS Volume Types](#EBS-Volume-Types)                                                                   |
| 6   | [EBS Multi-Attach](#EBS-Multi-Attach)                                                                   |
| 7   | [EBS Encryption](#EBS-Encryption)                                                                       |
| 8   | [Amazon EFS](#Amazon-EFS)                                                                               |
| 9   | [EFS Vs EBS](#EFS-Vs-EBS)                                                                               |
|     | **High Availability & Scalability**                                                                     |
| 1   | [Scalability & High Availability](#Scalability-&-High-Availability)                                     |
| 2   | [Elastic Load Balancing (ELB) Overview](<#Elastic-Load-Balancing-(ELB)-Overview>)                       |
| 3   | [Classic Load Balancers (CLB)](<#Classic-Load-Balancers-(CLB)>)                                         |
| 4   | [Application Load Balancer (ALB)](<#Application-Load-Balancer-(ALB)>)                                   |
| 5   | [Network Load Balancer (NLB)](<#Network-Load-Balancer-(NLB)>)                                           |
| 6   | [Gateway Load Balancer (GWLB)](<#Gateway-Load-Balancer-(GWLB)>)                                         |
| 7   | [Elastic Load Balancer - Sticky Sessions](#Elastic-Load-Balancer---Sticky-Sessions)                     |
| 8   | [Elastic Load Balancer - Cross Zone Load Balancing](#Elastic-Load-Balancer---Cross-Zone-Load-Balancing) |
| 9   | [Elastic Load Balancer - SSL Certificates](#Elastic-Load-Balancer---SSL-Certificates)                   |
| 10  | [Elastic Load Balancer - Connection Draining](#Elastic-Load-Balancer---Connection-Draining)             |
| 11  | [Auto Scaling Groups (ASG) Overview](<#Auto-Scaling-Groups-(ASG)-Overview>)                             |
| 12  | [Auto Scaling Groups - Scaling Policies](#Auto-Scaling-Groups---Scaling-Policies)                       |

## AWS

1. ### What is AWS?

   AWS (Amazon Web Services) is a comprehensive, evolving cloud computing platform provided by Amazon. It includes a mixture of **infrastructure-as-a-service (IaaS)**, **platform-as-a-service (PaaS)** and packaged **software-as-a-service (SaaS)** offerings. AWS offers tools such as compute power, database storage and content delivery services.

2. ### AWS Cloud Use Cases

   - AWS helps you create powerful and flexible apps that can grow as needed.
   - Suitable for many different types of businesses.
   - Here are some simplified use cases:
     - **Enterprise IT, Backup & Storage, Big Data Analytics:** This involves managing and storing data for large companies, analyzing that data for insights, and ensuring it's safely backed up.
     - **Website Hosting, Mobile & Social Apps:** Providing the infrastructure and support for hosting websites, mobile applications, and social media apps.
     - **Gaming:** Developing and/or hosting video games for various platforms.

3. ### Global Services

   - Identity and Access Management (IAM)
   - Route 53 (DNS service)
   - CloudFront (Content Delivery Network)
   - WAF (Web Application Firewall)

4. ### Region-scoped Services

   - Amazon EC2 (Infrastructure as a Service)
   - Elastic Beanstalk (Platform as a Service)
   - Lambda (Function as a Service)
   - Rekognition (Software as a Service)
   - [List of AWS Services Available by Region](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)

## IAM (AWS Identity and Access Management)

1. ### What is IAM?

   AWS Identity and Access Management (IAM) is like a bouncer for your AWS resources. It's a tool that lets you decide who gets into the party (your AWS resources) and what they're allowed to do once they're inside. So, you can manage who can access your stuff and what actions they can take, all from one central place.

2. ### IAM features

   - Shared access to your AWS account
   - Granular permissions
   - Secure access to AWS resources for applications that run on Amazon EC2
   - Multi-factor authentication (MFA)
   - Identity federation
   - Identity information for assurance
   - PCI DSS Compliance
   - Integrated with many AWS services
   - Eventually Consistent
   - Free to use

3. ### Accessing IAM

   - AWS Management Console (protected by password + MFA)
   - AWS Command Line Interface (CLI): protected by access keys
   - AWS Software Developer Kit (SDK) - for code: protected by access keys
   - IAM Query API

4. ### Users & Groups

   - Root account is automatically made, but don't use or share it.
   - Users are people within your organization, and can be grouped
   - Groups only contain users, not other groups
   - Users don’t have to belong to a group, and user can belong to multiple groups

   ![groupd](./assests/images/iam-groupd.png)

5. ### Permissions

   - **Users or Groups** can be assigned JSON documents called policies
   - These policies define the **permissions** of the users
   - In AWS you apply the **least privilege principle:** don’t give more permissions than a user needs

6. ### Policies Structure

   - Consists of

     - Version: policy language version,alwaysinclude “2012-10- 17”
     - Id: an identifier for the policy (optional)
     - Statement: one or more individual statements (required)

   - Statements consists of
     - Sid: an identifier for the statement (optional)
     - Effect: whether the statement allows or denies access (Allow, Deny)
     - Principal: account/user/role to which this policy applied to
     - Action: list of actions this policy allows or denies
     - Resource: list of resources to which the actions applied to
     - Condition: conditions for when this policy is in effect (optional)

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "FirstStatement",
      "Effect": "Allow",
      "Action": ["iam:ChangePassword"],
      "Resource": "*"
    },
    {
      "Sid": "SecondStatement",
      "Effect": "Allow",
      "Action": "s3:ListAllMyBuckets",
      "Resource": "*"
    },
    {
      "Sid": "ThirdStatement",
      "Effect": "Allow",
      "Action": [
        "s3:List*",
        "s3:Get*"
      ],
      "Resource": [
        "arn:aws:s3:::confidential-data",
        "arn:aws:s3:::confidential-data/*"
      ],
      "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}}
    }
  ]
}

```

7. ### Roles for Services

   - Some AWS service will need to perform actions on your behalf
   - To do so, we will assign permissions to AWS services with IAM Roles
   - Common roles:
     - EC2 Instance Roles
     - Lambda Function Roles
     - Roles for CloudFormation

8. ### Security Tools

   - IAM Credentials Report (account-level)
   - a report that lists all your account's users and the status of their various credentials

   - IAM Access Advisor (user-level)
     - Access advisor shows the service permissions granted to a user and when those services were last accessed.
     - You can use this information to revise your policies.

9. ### Guidelines & Best Practices

   - Don’t use the root account except for AWS account setup
   - One physical user = One AWS user
   - **Assign users to groups** and assign permissions to groups
   - Create a **strong password** policy
   - Use and enforce the use of **Multi Factor Authentication (MFA)**
   - Create and use **Roles** for giving permissions to AWS services
   - Use Access Keys for Programmatic Access (CLI / SDK)
   - Audit permissions of your account using IAM Credentials Report & IAM Access Advisor
   - **Never share IAM users & Access Keys**

## Amazon EC2 – Fundamentals

1.  ### What is Amazon EC2?

    - EC2 is one of the most popular of AWS’ offering
    - EC2 = Elastic Compute Cloud = Infrastructure as a Service
    - It mainly consists in the capability of :
      - Renting virtual machines (EC2 - Elastic Compute Cloud)
      - Storing data on virtual drives (EBS - Elastic Block Store)
      - Distributing load across machines (ELB - Elastic Load Balancing)
      - Scaling the services using an auto-scaling group (ASG - Auto Scaling Group )

2.  ### EC2 sizing & configuration options

    - Operating System: Linux, Windows or Mac OS
    - How much **CPU** and **RAM**
    - Storage space
      - Network-attached (**EBS** - Elastic Block Store & **EFS** - Elastic File System)
      - Hrdware (EC2 Instance Store)
    - Network card: Speed of the card, Public IP address
    - Firewall rules: Security group
    - Bootstrap script (configure at first launch): EC2 User Data
      - Used to automate boot tasks
        - Example:
          - Installing updates
          - Installing software
          - Downloading common files from the internet
          - Anything you can think of
      - Runs with the root user

3.  ### EC2 InstanceTypes - Overview

    - Different types of EC2 instances that are optimised for different use cases [Check here](https://aws.amazon.com/ec2/instance-types/)

    - **General Purpose** : M6a, M6g, M6gd, M6i, M6id, M6idn, M6in, M7a, M7g, M7gd, M7i, M7i-flex, T4g

      - Use cases:
        - Great for a diversity of workloads such as web servers or code repositories
          - Balance between:
            - Compute
            - Memory
            - Networking
      - Series:
        - A Series (Medium, Large) : A1
        - M Series (Large) : M4, M5, M5a, M5ad, M5d
        - T Series : T2, T3, T3a

    - **Compute Optimized** :

      - Use cases:

        - Great for compute-intensive tasks that require high performance processors:
          - Web Server
          - Batch processing workloads
          - Media transcoding
          - High performance web servers
          - High performance computing (HPC)
          - Scientific modeling & machine learning

      - Series:
        - C Series : C4, C5, C5n, C6a, C6g, C6gd, C6gn, C6i, C6id, C6in, C7a, C7g, C7gd, C7gn, C7i

    - **Memory Optimized** : R6a, R6g, R6gd, R6i, R6id, R6idn, R6in, R7a, R7g, R7gd, R7i, R7iz, X2gd, X2idn, X2iedn

      - Use cases:

        - Fast performance for workloads that process large data sets in memory
        - High performance, relational/non-relational databases
        - Distributed web scale cache stores
        - In-memory databases optimized for BI (business intelligence)
        - Applications performing real-time processing of big unstructured data

      - Series:
        - R Series : R4, R5, R5a, R5d
        - X Series : X1, X1e
        - Z Series : Z1d

    - **Accelerated Computing** : DL2q, G5g, Inf2, P5, Trn1, Trn1n

      - Use cases:

        - Accelerated computing instances use hardware accelerators or co-processors.
        - They perform functions like floating-point number calculations, graphics processing, or data pattern matching.
        - These functions are done more efficiently compared to software running on CPUs.

      - Series:
        - P Series : P2, P3
        - G Series : G2, G3
        - F Series : F1

    - **Storage Optimized** : I4g, I4i, Im4gn, Is4gen

      - Use cases:

        - Designed for workloads needing high sequential read/write access to large data sets
        - Optimized for delivering tens of thousands of low-latency, random IOPS
        - Ideal for applications with heavy data processing needs
        - Local storage ensures faster access compared to network storage
        - Suitable for data-intensive tasks like database management, analytics, and data warehousing

      - Series:
        - I Series : I3, I3e
        - D Series : D2
        - H Series : H1

    - **HPC Optimized (High performance computing)** : Hpc6a, Hpc6id, Hpc7a, Hpc7g

      - Use cases:

        - HPC instances on AWS are designed for running high-performance computing workloads efficiently.
        - They offer optimized price-performance for scaling HPC tasks.
        - Ideal for applications requiring robust processing power, like complex simulations and deep learning tasks.
        - Suited for large-scale operations where performance is critical.
        - Tailored with high-performance processors to enhance computational capabilities.

      - Series:
        - U Series : U6, U9, U12

    - **Previous Generation Instance** :

      - Series:
        - T1, M1, C1, CC2, M2, CR1, CG1, i2, HS1, M3,C3, R3

    - **Instance Features**

      - Use cases:

        - **Scalability**: Easily scale your applications up or down based on demand.
        - **Management Tools**: Access a variety of tools to streamline deployment and management processes.
        - **Monitoring**: Monitor the performance of your applications in real-time.
        - **Flexibility**: Choose from a wide range of instance types to suit your specific needs.
        - **Security**: Benefit from built-in security features to protect your applications and data.
        - **Integration**: Seamlessly integrate with other AWS services for enhanced functionality.
        - **Cost-Effectiveness**: Pay only for the resources you use, with cost-effective pricing models.
        - **Reliability**: Rely on Amazon's robust infrastructure for high availability and reliability.

        - Burstable Performance Instances
        - Multiple Storage Options
        - EBS-optimized Instances
        - Cluster Networking
        - Intel Processor Features

    - **Measuring Instance Performance**

      - Use cases:

            - Amazon EC2 offers various instance types with different specifications:
              - CPU
              - Memory
              - Disk
              - Networking
            - Launching new instances and running tests simultaneously is straightforward.
            - It's advised to measure application performance to select suitable instance types and confirm application architecture.
            - Rigorous load and scale testing is recommended to ensure desired application scalability.

    > [!NOTE]
    > We can make 20 instance in a region and if we require more than we need to request AWS.

4.  ### EC2 InstanceTypes - Example

    - ![ec2-instance-example](./assests/images/ec2-instance-example.png)
    - **_t2.micro is part of the AWS free tier (up to 750 hours per month)_**
    - For more details [check here](https://instances.vantage.sh/)

5.  ### Introduction to Security Groups

    - Fundamental of network security in AWS
    - They control how traffic is allowed into or out of our EC2 Instances.
      - Inbound traffic
      - Outbound traffic
    - Only contain **allow** rules
    - Rules can reference by IP or by security group
    - Acting as a “firewall” on EC2 instances
      - Access to Ports
      - Authorised IP ranges – IPv4 and IPv6
      - Control of inbound network (from other to the instance)
      - Control of outbound network (from the instance to other)
    - Can be attached to multiple instances
    - It’s good to maintain one separate security group for SSH access
    - All inbound traffic is **blocked** by default
    - All outbound traffic is **authorised** by default

6.  ### Classic Ports

    - 22 = SSH (Secure Shell) - log into a Linux instance
    - 21 = FTP (File Transfer Protocol) – upload files into a file share
    - 22 = SFTP (Secure File Transfer Protocol) – upload files using SSH
    - 80 = HTTP – access unsecured websites
    - 443 = HTTPS – access secured websites
    - 3389 = RDP (Remote Desktop Protocol) – log into a Windows instance

7.  ### SSH Summary Table

    |              | SSH | Putty | EC2 Instance Connect |
    | ------------ | --- | ----- | -------------------- |
    | Mac          | ☑   |       | ☑                    |
    | Linux        | ☑   |       | ☑                    |
    | Window < 10  |     | ☑     | ☑                    |
    | Window >= 10 | ☑   | ☑     | ☑                    |

    - SSH using mac:

      - ssh -i EC2-instatnce-key ec2-user@<public-ip> (ex: ec2-user@35.180.242.162)
      - ssh -i ec2-test-v2.pem ec2-user@35.180.242.162

    - EC2 Instance Connect
      - Connect to your EC2 instance within your browser
      - No need to use your key file that was downloaded (Works only out-of-the-box with Amazon Linux 2)
      - Goto EC2 > Instances > <your-instance> > Connect to instance > Connect action

8.  ### EC2 Instances Purchasing Options

    - **On-Demand Instances** – short workload, predictable pricing, pay by second

      - Pay for what you use:
        - Linux or Windows - billing per second, after the first minute
        - All other operating systems - billing per hour
      - Has the highest cost but no upfront payment
      - No long-term commitment
      - Recommended for short-term and un-interrupted workloads, where you can't predict how the application will behave

    - **Reserved/Schedule Instances** (1 & 3 years)

      - Reserved Instances – long workloads
      - Convertible Reserved Instances – long workloads with flexible instances
      - You reserve a specific instance attributes (Instance Type, Region,Tenancy, OS)
      - Reservation Period – 1 year (+discount) or 3 years (+++discount)
      - Payment Options – No Upfront (+), Par tial Upfront (++), All Upfront (+++)
      - Reserved Instance’s Scope – Regional or Zonal (reserve capacity in an AZ)
      - Recommended for steady-state usage applications (think database)
      - You can buy and sell in the Reserved Instance Marketplace
      - Convertible Reserved Instance
      - Can change the EC2 instance type, instance family, OS, scope and tenancy - Up to 66% discount

    - **Savings Plans** (1 & 3 years) – commitment to an amount of usage, long workload - Spot Instances – short workloads, cheap, can lose instances (less reliable)

      - Get a discount based on long-term usage (up to 72% - same as RIs)
      - Commit to a certain type of usage ($10/hour for 1 or 3 years)
      - Usage beyond EC2 Savings Plans is billed at the On-Demand price
      - Locked to a specific instance family & AWS region (e.g., M5 in us-east-1)
      - Flexible across:
        - Instance Size (e.g., m5.xlarge, m5.2xlarge)
        - OS (e.g., Linux, Windows)
        - Tenancy (Host, Dedicated, Default)

    - **Spot Instances** -

      - Can get a discount of up to 90% compared to On-demand
      - Instances that you can “lose” at any point of time if your max price is less than the current spot price
      - The MOST cost-efficient instances in AWS
      - Useful for workloads that are resilient to failure
        - Batch jobs
        - Data analysis
        - Image processing
        - Any distributed workloads
        - Workloads with a flexible start and end time
      - Not suitable for critical jobs or databases

    - **Dedicated Hosts** – book an entire physical server, control instance placement

      - A physical server with EC2 instance capacity fully dedicated to your use
      - Allows you address **compliance requirements** and **use your existing server- bound software licenses** (per-socket, per-core, pe—VM software licenses)
      - Purchasing Options:
        - **On-demand** – pay per second for active Dedicated Host
        - **Reserved** - 1 or 3 years (No Upfront, Partial Upfront,All Upfront)
      - The most expensive option
      - Useful for software that have complicated licensing model (BYOL – Bring Your
        Own License)
      - Or for companies that have strong regulatory or compliance needs

    - **Dedicated Instances** – no other customers will share your hardware

      - Instances run on hardware that’s dedicated to you
      - May share hardware with other instances in same account
      - No control over instance placement (can move hardware after Stop / Start)

    - ![dedicated-instance-vs-host](./assests/images/dedicated-instance-vs-host.png)

    - **Capacity Reservations** – reserve capacity in a specific AZ for any duration

      - Reserve On-Demand instances capacity in a specific AZ for any duration
      - You always have access to EC2 capacity when you need it
      - No time commitment (create/cancel anytime), no billing discounts
      - Combine with Regional Reserved Instances and Savings Plans to benefit from billing discounts
      - You’re charged at On-Demand rate whether you run instances or not
      - Suitable for short-term, uninterrupted workloads that needs to be in a specific AZ

    - **EC2 Spot Instance Requests**

      - Can get a discount of up to 90% compared to On-demand
      - Define **max spot price** and get the instance while **current spot price** < **max**
        - If the current spot price > your max price you can choose to stop or terminate your instance with a 2 minutes grace period.
      - Used for batch jobs, data analysis, or workloads that are resilient to failures.
      - Not great for critical jobs or databases

    - **Spot Fleets**
      - Spot Fleets = set of Spot Instances + (optional) On-Demand Instances
      - The Spot Fleet will try to meet the target capacity with price constraints
      - Strategies to allocate Spot Instances:
        - lowestPrice: from the pool with the lowest price (cost optimization, short workload)
        - diversified: distributed across all pools (great for availability, long workloads)
        - capacityOptimized: pool with the optimal capacity for the number of instances
        - priceCapacityOptimized (recommended): pools with highest capacity available, then select the pool with the lowest price (best choice for most workloads)
      - Spot Fleets allow us to automatically request Spot Instances with the lowest price

## Amazon EC2 – Solutions Architect Associate Level

1. ### Private vs Public IP (IPv4)

- Networking has two sorts of IPs. IPv4 and IPv6:
  - IPv4:1.160.10.240
  - IPv6:3ffe:1900:4545:3:200:f8ff:fe21:67cf
- IPv4 is still the most common format used online.
- IPv6 is **newer** and solves problems for the Internet of Things (IoT).
- IPv4 allows for 3.7 billion different addresses in the public space
- IPv4: [0-255].[0-255].[0-255].[0-255].

- **Public IP:**

  - Public IP means the machine can be identified on the internet (WWW)
  - Must be unique across the whole web (not two machines can have the same public IP).
  - Can be geo-located easily

- **Private IP:**

  - Private IP means the machine can only be identified on a private network only
  - The IP must be unique across the private network
  - BUT two different private networks (two companies) can have the same IPs.
  - Machines connect to WWW using a NAT + internet gateway (a proxy)
  - Only a specified range of IPs can be used as private IP

- **Elastic IP:**

  - When you stop and then start an EC2 instance, it can change its public IP.
  - If you need to have a fixed public IP for your instance, you need an Elastic IP
  - An Elastic IP is a public IPv4 IP you own as long as you don’t delete it
  - You can attach it to one instance at a time
  - You can only have 5 Elastic IP in your account (you can ask AWS to increase that).

2. ### Placement groups

- To handle your workload better, you can put a bunch of connected EC2 computers together in a placement group to control where they go.
- Depending on what you're doing, you can set up a placement group in different ways:

  - **Cluster** : Grouping instances into a low-latency cluster within one Availability Zone.

    Pros:

    - Excellent network speed (10 Gbps bandwidth) when using Enhanced Networking.

    Cons:

    - If the rack (a collection of servers) fails, all instances (computing units) fail simultaneously.

    Use Case:

    - Big Data tasks requiring speedy completion.
    - Applications demanding ultra-low latency and high network speed.

  - **Partition** : Distribute tasks to different pieces of equipment (up to 7 tasks per group in each area).

    Pros:

    - **Availability:** Spans across different availability zones (AZs), enhancing availability.
    - **Reduced Risk:** Decreases the risk of simultaneous failures.
    - **Isolation:** EC2 instances are on separate physical hardware, reducing the impact of hardware failures.

    Cons:

    - **Limitation:** Restricted to 7 instances per AZ per placement group.

    Use Case:

    - **Maximized Availability:** Ideal for applications needing maximum uptime.
    - **Critical Applications:** Ensures isolation between instances, crucial for critical applications to prevent failure cascades.

  - **Spread** : Distributing tasks or data across various sections (called partitions), each using different groups of servers within a single availability zone (AZ). It can handle hundreds of virtual servers (EC2 instances) per category (like Hadoop, Cassandra, or Kafka).

    - Each "zone" (AZ) can have up to 7 separate parts.
    - These parts can spread out across multiple zones.
    - Hundreds of EC2 instances can be in use.
    - Instances within a part don't share space with those in other parts.
    - If one part fails, it only affects the instances in that part, not others.
    - EC2 instances can access part-specific info.
    - It's handy for systems like HDFS, HBase, Cassandra, or Kafka.

3. ### Elastic Network Interfaces (ENI)

- Logical component in a VPC that represents a **virtual network card**
- The ENI can have the following attributes:
  - Primary private IPv4, one or more secondary IPv4
  - A primary IPv6 address from the IPv6 address range of your VPC
  - One or more secondary private IPv4 addresses from the IPv4 address range of your VPC
  - One Elastic IP (IPv4) per private IPv4
  - One Public IPv4
  - One or more IPv6 addresses
  - One or more security groups
  - A MAC address
  - A source/destination check flag
  - A description

4. ### EC2 Hibernate

- EC2 Hibernate:

  - The in-memory (RAM) state is preserved
  - The instance boot is much faster! (the OS is not stopped / restarted)
  - Under the hood: the RAM state is written to a file in the root EBS volume
  - The root EBS volume must be encrypted

- Use cases:

  - Long-running processing
  - Saving the RAM state
  - Services that take time to initialize

- Good to know
  - Supported Instance Families – C3, C4, C5, I3, M3, M4, R3, R4,T2,T3, ...
  - Instance RAM Size – must be less than 150 GB.
  - Instance Size – not supported for bare metal instances.
  - AMI – Amazon Linux 2, Linux AMI, Ubuntu, RHEL, CentOS & Windows...
  - Root Volume – must be EBS, encrypted, not instance store, and large
  - Available for On-Demand, Reser ved and Spot Instances
  - An instance can NOT be hibernated more than 60 days

## Amazon EC2 – Instance Storage

1. ### EBS Overview

- An EBS (**Elastic Block Store**) Volume is a network drive you can attach to your instances while they run
- It allows your instances to persist data, even after their termination
- They can only be mounted to one instance at a time (at the CCP level)
- They are bound to a specific availability zone
- Analogy:Think of them as a “network USB stick”
- Free tier: 30 GB of free EBS storage of type General Purpose (SSD) or Magnetic per month

- It’s a network drive (i.e. not a physical drive)
  - It uses the network to communicate the instance, which means there might be a bit of latency
  - It can be detached from an EC2 instance and attached to another one quickly
- It’s locked to an Availability Zone (AZ)
  - An EBS Volume in us-east-1a cannot be attached to us-east-1b
  - To move a volume across, you first need to snapshot it
- Have a provisioned capacity (size in GBs, and IOPS)

  - You get billed for all the provisioned capacity
  - You can increase the capacity of the drive over time

- Controls the EBS behaviour when an EC2 instance terminates
  - By default, the root EBS volume is deleted (attribute enabled)
  - By default, any other attached EBS volume is not deleted (attribute disabled)
- This can be controlled by the AWS console / AWS CLI
- **Use case**: preserve root volume when instance is terminated

2. ### EBS Snapshots

- Make a backup (snapshot) of your EBS volume at a point in time
- Not necessary to detach volume to do snapshot, but recommended
- Can copy snapshots across AZ or Region

- **Features**
  - EBS Snapshot Archive
    > Move a Snapshot to an "archive tier".
    > Restoring from the archive takes 24 to 72 hours.
  - Recycle Bin for EBS Snapshots
    > To retain deleted snapshots for recovery after accidental deletion
    > Specify retention (from 1 day to 1 year)
  - Fast Snapshot Restore (FSR)
    > Force full initialization of snapshot to have no latency on the first use ($$$)

3. ### AMI Overview

- AMI = Amazon Machine Image
- AMI are a customization of an EC2 instance
  - You add your own software, configuration, operating system, monitoring...
  - Faster boot / configuration time because all your software is pre-packaged
- AMI are built for a **specific region** (and can be copied across regions)
- You can launch EC2 instances from:

  - **A Public AMI **: AWS provided
  - **Your own AMI **: you make and maintain them yourself
  - **An AWS Marketplace AMI **: an AMI someone else made (and potentially sells)

- AMI Process (from an EC2 instance)
  - Start an EC2 instance and customize it
  - Stop the instance (for data integrity)
  - Build an AMI – this will also create EBS snapshots
  - Launch instances from other AMIs

4. ### EC2 Instance Store

- EBS volumes are network drives with good but “limited” performance
- _**If you need a high-performance hardware disk, use EC2 Instance Store**_
- Better I/O performance
- EC2 Instance Store lose their storage if they’re stopped (ephemeral)
- Good for buffer / cache / scratch data / temporary content
- Risk of data loss if hardware fails
- Backups and Replication are your responsibility

5. ### EBS Volume Types

- EBS Volumes types

  1. - General Purpose SSD (gp3, gp2): General purpose SSD volume that balances price and performance for a wide variety of workloads
  2. - Provisioned IOPS(Input/Output Operations Per Second) SSD (io2, io1): Highest-performance SSD volume for mission-critical low-latency or high-throughput workloads
  3. - Throughput Optimized HDD (st1): Low cost HDD volume designed for frequently accessed, throughput- intensive workloads
  4. - Cold HDD (sc1): Lowest cost HDD volume designed for less frequently accessed workloads

- **Only gp2/gp3 and io1/io2 Block Express can be used as boot volumes**

6. ### EBS Multi-Attach

- Attach the same EBS volume to multiple EC2 instances in the same AZ
- Each instance has full read & write permissions to the high-performance volume
- Use case:
  - Achieve **higher application availability** in clustered Linux applications (ex:Teradata)
  - Applications must manage concurrent write operations
- Up to 16 EC2 Instances at a time
- Must use a file system that’s cluster-aware (not XFS, EXT4, etc...)

7. ### EBS Encryption

- When you create an encrypted EBS volume, you get the following:
  - Data at rest is encrypted inside the volume
  - All the data in flight moving between the instance and the volume is encrypted
  - All snapshots are encrypted
  - All volumes created from the snapshot
- Encryption and decryption are handled transparently (you have nothing to do)
- Encryption has a minimal impact on latency
- EBS Encryption leverages keys from KMS (AES-256)
- Copying an unencrypted snapshot allows encryption
- Snapshots of encrypted volumes are encrypted

- **Encrypt an unencrypted EBS volume**
  - Create an EBS snapshot of the volume
  - Encrypt the EBS snapshot (using copy)
  - Create new ebs volume from the snapshot (the volume will also be encrypted)
  - Now you can attach the encrypted volume to the original instance

8. ### Amazon EFS

- EFS - Elastic File System
- Managed NFS (Network File System) that can be mounted on many EC2
- EFS works with EC2 instances in multi-AZ
- Highly available, scalable, expensive (3x gp2), pay per use
- Use cases: content management, web serving, data sharing,Wordpress
- Uses NFSv4.1 protocol
- Uses security group to control access to EFS
- Compatible with Linux based AMI (not Windows)
- Encryption at rest using KMS
- POSIX file system (~Linux) that has a standard file API
- File system scales automatically, pay-per-use, no capacity planning!

- **Performance & Storage Classes**

  - EFS Scale

    - 1000s of concurrent NFS clients, 10 GB+ /s throughput
    - Grow to Petabyte-scale network file system, automatically

  - Performance Mode (set at EFS creation time)

    - General Purpose (default) – latency-sensitive use cases (web server, CMS, etc...)
    - Max I/O – higher latency, throughput, highly parallel (big data, media processing)

  - Throughput Mode
    - Bursting – 1TB = 50MiB/s + burst of up to 100MiB/s
    - Provisioned – set your throughput regardless of storage size, ex: 1 GiB/s for 1 TB storage
    - Elastic – automatically scales throughput up or down based on your workloads
    - Upto3GiB/sforreadsand1GiB/sforwrites
    - Usedforunpredictableworkloads

- **Storage Classes**

  - Storage Tiers (lifecycle management feature – move file after N days)

    - Standard: for frequently accessed files
    - Infrequent access (EFS-IA): cost to retrieve files, lower price to store. Enable EFS-IA with a Lifecycle Policy

  - Availability and durability
    - Standard: Multi-AZ, great for prod
    - One Zone: One AZ, great for dev, backup enabled by default, compatible with IA (EFS One Zone-IA)

  > Over 90% in cost savings

9. ### EFS Vs EBS

- EBS volumes
  - one instance (except multi-attach io1/io2)
  - are locked at the Availability Zone (AZ) level
  - gp2: IO increases if the disk size increases
  - gp3 & io1: can increase IO independently
- To migrate an EBS volume across AZ
  - Take a snapshot
  - Restore the snapshot to another AZ
  - EBS backups use IO and you shouldn’t run them while your application is handling a lot of traffic
- Root EBS Volumes of instances get terminated by default if the EC2 instance gets terminated. (you can disable that)

- Mounting 100s of instances across AZ
- EFS share website files (WordPress)
- Only for Linux Instances (POSIX)
- EFS has a higher price point than EBS
- Can leverage EFS-IA for cost savings

## High Availability & Scalability

1. ### Scalability & High Availability

- Scalability means that an application / system can handle greater loads by adapting.
- There are two kinds of scalability:
  - Vertical Scalability
  - Horizontal Scalability (= elasticity)
- Scalability is linked but different to High Availability

- **Vertical Scalability**

  - Vertically scalability means increasing the size of the instance
  - For example, your application runs on a t2.micro
  - Scaling that application vertically means running it on a t2.large
  - Vertical scalability is very common for non distributed systems, such as a database.
  - RDS, ElastiCache are services that can scale ver tically.
  - There’s usually a limit to how much you can vertically scale (hardware limit)

- **Horizontal Scalability**

  - Horizontal Scalability means increasing the number of instances / systems for your application
  - Horizontal scaling implies distributed systems.
  - This is very common for web applications / modern applications

- **High Availability**

  - High Availability usually goes hand in hand with horizontal scaling
  - High availability means running your application / system in at least 2 data centers (== Availability Zones)
  - The goal of high availability is to survive a data center loss
  - The high availability can be passive (for RDS Multi AZ for example)
  - The high availability can be active (for horizontal scaling)

- **High Availability & Scalability For EC2**
- Vertical Scaling: Increase instance size (= scale up / down)
  - From: t2.nano - 0.5G of RAM, 1 vCPU
  - To: u-12tb1.metal – 12.3 TB of RAM, 448 vCPUs
- Horizontal Scaling: Increase number of instances (= scale out / in)
  - Auto Scaling Group
  - Load Balancer
- High Availability: Run instances for the same application across multi AZ
  - Auto Scaling Group multi AZ
  - Load Balancer multi AZ

2. ### Elastic Load Balancing (ELB) Overview

- Load Balances are servers that forward traffic to multiple servers (e.g., EC2 instances) downstream
- **Why use a load balancer?**
  - Spread load across multiple downstream instances
  - Expose a single point of access (DNS) to your application
  - Seamlessly handle failures of downstream instances
  - Do regular health checks to your instances
  - Provide SSL termination (HTTPS) for your websites
  - Enforce stickiness with cookies
  - High availability across zones
  - Separate public traffic from private traffic
- **Why use an Elastic Load Balancer?**
  - An Elastic Load Balancer is a managed load balancer
    - AWS guarantees that it will be working
    - AWS takes care of upgrades, maintenance, high availability
    - AWS provides only a few configuration knobs
  - It costs less to setup your own load balancer but it will be a lot more effort on your end
  - It is integrated with many AWS offerings / services
    - EC2, EC2 Auto Scaling Groups, Amazon ECS
    - AWS Certificate Manager (ACM), CloudWatch
    - Route53,AWSWAF,AWSGlobalAccelerator
- **Health Checks**
  - Health Checks are crucial for Load Balancers
  - They enable the load balancer to know if instances it forwards traffic to are available to reply to requests
  - The health check is done on a port and a route (/health is common)
  - If the response is not 200 (OK), then the instance is unhealthy
- **Types of load balancer on AWS**
  - 1.  **Classic Load Balancer** (v1 - old generation) – 2009 – CLB - HTTP, HTTPS,TCP,SSL(secureTCP)
  - 2.  **Application Load Balancer** (v2 - new generation) – 2016 – ALB - HTTP, HTTPS,WebSocket
  - 3.  **Network Load Balancer** (v2 - new generation) – 2017 – NLB - TCP,TLS(secureTCP),UDP
  - 4.  **Gateway Load Balancer** – 2020 – GWLB - Operates at layer 3 (Network layer) – IP Protocol

> Overall, it is recommended to use the newer generation load balancers as they provide more features
> Some load balancers can be setup as internal (private) or external (public) ELBs

- Suppor HTTP, HTTPS, TCP, SSL
- Health checks are TCP or HTTP based
- Protocols port supported are 1-65535
- It's support IPv4, IPv6 and dual stack
- Fixed hostname XXX.region.elb.amazonaws.com

4. ### Application Load Balancer (ALB)

- Application load balancers is Layer 7 (HTTP)
- Distributes incoming application traffic across multiple targest such as EC2 instances in multiple AZ.
- Increase the availability of your application
- Suppor t for HTTP/2 and WebSocket
- Support redirects (from HTTP to HTTPS for example)
- Routing tables to different target groups:
  - Routing based on path in URL (example.com/users & example.com/posts)
  - Routing based on hostname in URL (one.example.com & other.example.com)
  - Routing based on Query String, Headers (example.com/users?id=123&order=false)
- ALB are a great fit for micro services & container-based application (example: Docker & Amazon ECS)
- Has a port mapping feature to redirect to a dynamic port in ECS
- Target Groups:
  - EC2 instances (can be managed by an Auto Scaling Group) – HTTP
  - ECS tasks (managed by ECS itself) – HTTP
  - Lambda functions – HTTP request is translated into a JSON event
  - IP Addresses – must be private IPs
  - ALB can route to multiple target groups
  - Health checks are at the target group level
- Fixed hostname XXX.region.elb.amazonaws.com
- The application servers don’t see the IP of the client directly
  - The true IP of the client is inserted in the header **X-Forwarded-For**
  - We can also get Port (X-Forwarded-Port) and proto (X-Forwarded-Proto)

5. ### Network Load Balancer (NLB)

- Network load balancers (Layer 4) allow to:
  - Forward TCP & UDP traffic to your instances
  - Handle millions of request per seconds
  - Less latency ~100 ms (vs 400 ms for ALB)
- NLB has one static IP per AZ, and supports assigning Elastic IP (helpful for whitelisting specific IP)
- Used for extreme performance,TCP or UDP traffic
- Not included in the AWS free tier
- Target Groups:
  - EC2 instances
  - IP Addresses – must be private IPs
  - Application Load Balancer
  - Health Checks support the TCP, HTTP and HTTPS Protocols

6. ### Gateway Load Balancer (GWLB)

- GWLB is a Layer-3 (Network Layer) Service
- GWLB is service designed to help you deploy, scale and manage virtual appliances, susch as (Firewall, Intrusion Detection System (IDS), Intrusion Prevention System)
- Its distribute traffic across multiple appliances, perfrom helth check and supports Equals-Cost Multi-path routing (ECMP) for high avaibility and throughput.
- Deploy, scale, and manage a fleet of 3rd party network virtual appliances in AWS
- Example: Firewalls, Intrusion Detection and Prevention Systems, Deep Packet Inspection Systems, payload manipulation, ...
- Combines the following functions:
  - Transparent Network Gateway – single
  - Load Balancer – distributes traffic to your virtual appliances
- Uses the **GENEVE** protocol on port 6081
- Target Groups:
  - EC2 instances
  - IP Addresses – must be private IPs
- Benefits:
  - Deploy third-party virtual appliances faster
  - Scale virtual appliances while managing costs
  - Improve virtual appliance availability

7. ### Elastic Load Balancer - Sticky Sessions

- It is possible to implement stickiness so that the same client is always redirected to the same instance behind a load balancer
- This works for Classic Load Balancer, Application Load Balancer, and Network Load Balancer
- For both CLB & ALB, the **“cookie”** used for stickiness has an expiration date you control
- Use case: make sure the user doesn’t lose his session data
- Enabling stickiness may bring imbalance to the load over the backend EC2 instances
- Sticky Sessions – Cookie Names
  - Application-based Cookies
    - Custom cookie
      - Generated by the target
      - Can include any custom attributes required by the application
      - Cookie name must be specified individually for each target group
      - Don’t use AWSALB, AWSALBAPP, or AWSALBTG (reserved for use by the ELB)
    - Application cookie
      - Generated by the load balancer
      - Cookie name is AWSALBAPP
  - Duration-based Cookies
    - Cookie generated by the load balancer
    - Cookie name is AWSALB for ALB, AWSELB for CLB

8. ### Elastic Load Balancer - Cross Zone Load Balancing

- Each load balancer instance distributes evenly across all registered instances in all AZ
- Application Load Balancer
  - Enabled by default (can be disabled at the Target Group level)
  - No charges for inter AZ data
- Network Load Balancer & Gateway Load Balancer
  - Disabled by default
  - You pay charges ($) for inter AZ data if enabled
- Classic Load Balancer
  - Disabled by default
  - No charges for inter AZ data if enabled

9. ### Elastic Load Balancer - SSL Certificates

- SSL/TLS - Basics
  - An SSL Certificate allows traffic between your clients and your load balancer to be encrypted in transit (in-flight encryption)
  - SSL refers to Secure Sockets Layer, used to encrypt connections
  - TLS refers to Transport Layer Security, which is a newer version
  - Nowadays, TLS cer tificates are mainly used, but people still refer as SSL
  - Public SSL certificates are issued by Certificate Authorities (CA)
  - Comodo, Symantec, GoDaddy, GlobalSign, Digicert, Letsencrypt, etc...
  - SSL certificates have an expiration date (you set) and must be renewed
- Load Balancer - SSL Certificates
  - The load balancer uses an X.509 certificate (SSL/TLS server certificate)
  - You can manage certificates using ACM (AWS Certificate Manager)
  - You can create upload your own certificates alternatively
  - HTTPS listener:
    - You must specify a default certificate
    - You can add an optional list of certs to support multiple domains
    - Clients can use SNI (Server Name Indication) to specify the hostname they reach
    - Ability to specify a security policy to support older versions of SSL /TLS (legacy clients)
- SSL – Server Name Indication (SNI)
  - SNI solves the problem of loading multiple SSL certificates onto one web server (to serve multiple websites)
  - It’s a “newer” protocol, and requires the client to indicate the hostname of the target server in the initial SSL handshake
  - The server will then find the correct certificate, or return the default one

> Note: Only works for ALB & NLB (newer generation), CloudFront - Does not work for CLB (older gen)

- SSL Certificates:
- Classic Load Balancer (v1)
  - Support only one SSL certificate
  - Must use multiple CLB for multiple hostname with multiple SSL certificates
- Application Load Balancer (v2)
  - Supports multiple listeners with multiple SSL certificates
  - Uses Server Name Indication (SNI) to make it work
- Network Load Balancer (v2)
  - Supports multiple listeners with multiple SSL certificates
  - Uses Server Name Indication (SNI) to make it work

10. ### Elastic Load Balancer - Connection Draining

- Feature naming
  - Connection Draining – for CLB
  - Deregistration Delay – for ALB & NLB
- Time to complete “in-flight requests” while the instance is de-registering or unhealthy
- Stops sending new requests to the EC2 instance which is de-registering
- Between 1 to 3600 seconds (default: 300 seconds)
- Can be disabled (set value to 0)
- Set to a low value if your requests are short

11. ### Auto Scaling Groups (ASG) Overview
12. ### Auto Scaling Groups - Scaling Policies

======================================================================================================================================

# 🛡️ License

This project is licensed under the MIT License - see the [`LICENSE`](LICENSE) file for details.

# 👨‍💻 Author

### 👤 Asif Vora

- Github: [@asifvora](https://github.com/asifvora)
- LinkedIn: [@asif-vora](https://www.linkedin.com/in/asif-vora/)
- Twitter: [@007_dark_shadow](https://twitter.com/007_dark_shadow)
- Instagram: [@007_dark_shadow](https://www.instagram.com/007_dark_shadow/)

# 🍰 Contributing

- Please contribute using [GitHub Flow](https://guides.github.com/introduction/flow). Create a branch, add commits, and [open a pull request](https://github.com/asif-simform/MERN-Stack/compare).

- Please read [`CONTRIBUTING`](CONTRIBUTING.md) for details.

# 🙏 Support

This project needs a ⭐️ from you. Don't forget to leave a star ⭐️
