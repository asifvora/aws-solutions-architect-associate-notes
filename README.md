# Aws Solutions Architect Associate Notes

> Click ⭐ if you like the project.

## Visit Document Website

https://aws-solutions-architect-associate-notes.vercel.app

### Table of Contents

| No. | Questions                                                                 |
| --- | ------------------------------------------------------------------------- |
|     | **AWS**                                                                   |
| 1   | [What is AWS?](#what-is-AWS)                                              |
| 2   | [AWS Cloud Use Cases](#AWS-Cloud-Use-Cases)                               |
| 3   | [Global Services](#Global-Services)                                       |
| 4   | [Region-scoped Services](#Region-scoped-Services)                         |
|     | **AWS IAM (AWS Identity and Access Management)**                          |
| 1   | [What is IAM?](#what-is-IAM)                                              |
| 2   | [IAM features](#IAM-features)                                             |
| 3   | [Accessing IAM](#Accessing-IAM)                                           |
| 4   | [Users & Groups](#Users-&-Groups)                                         |
| 5   | [Permissions](#Permissions)                                               |
| 6   | [Roles for Services](#Roles-for-Services)                                 |
| 7   | [Permissions](#Permissions)                                               |
| 8   | [Security Tools](#Security-Tools)                                         |
| 9   | [Guidelines & Best Practices](#Guidelines-&-Best-Practices)               |
|     | **Amazon EC2 – Basics**                                                   |
| 1   | [What is Amazon EC2?](#what-is-Amazon-EC2)                                |
| 2   | [EC2 sizing & configuration options](#EC2-sizing-&-configuration-options) |
| 3   | [EC2 InstanceTypes - Overview](#EC2-InstanceTypes---Overview)             |

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

## Amazon EC2 – Basics

1. ### What is Amazon EC2?

   - EC2 is one of the most popular of AWS’ offering
   - EC2 = Elastic Compute Cloud = Infrastructure as a Service
   - It mainly consists in the capability of :
     - Renting virtual machines (EC2 - Elastic Compute Cloud)
     - Storing data on virtual drives (EBS - Elastic Block Store)
     - Distributing load across machines (ELB - Elastic Load Balancing)
     - Scaling the services using an auto-scaling group (ASG - Auto Scaling Group )

2. ### EC2 sizing & configuration options

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

3. ### EC2 InstanceTypes - Overview

   - Different types of EC2 instances that are optimised for different use cases [Check here](https://aws.amazon.com/ec2/instance-types/)

     - **General Purpose**

       - Use cases:
         - General purpose instances offer balanced compute, memory, and networking resources.
         - Suitable for diverse workloads requiring a mix of these resources.
         - Ideal for applications like web servers and code repositories.
         - Provide versatility for various tasks without specializing in one resource type.

     - **Compute Optimized**

       - Use cases:
         - Compute Optimized instances are designed for applications that require high-performance processors.
         - Ideal for compute-bound tasks that demand significant processing power.
         - Suited for batch processing, media transcoding, high-performance web servers, and scientific modeling.
         - Also beneficial for high-performance computing (HPC), dedicated gaming servers, and ad server engines.
         - Suitable for machine learning inference and other compute-intensive applications.

     - **Memory Optimized**

       - Use cases:
         - Designed for fast performance
         - Ideal for workloads handling large data sets in memory

     - **Accelerated Computing**

       - Use cases:
         - Accelerated computing instances use hardware accelerators or co-processors.
         - They perform functions like floating-point number calculations, graphics processing, or data pattern matching.
         - These functions are done more efficiently compared to software running on CPUs.

     - **Storage Optimized**

       - Use cases:
         - Designed for workloads needing high sequential read/write access to large data sets
         - Optimized for delivering tens of thousands of low-latency, random IOPS
         - Ideal for applications with heavy data processing needs
         - Local storage ensures faster access compared to network storage
         - Suitable for data-intensive tasks like database management, analytics, and data warehousing

     - **HPC Optimized (High performance computing)**

       - Use cases:
         - HPC instances on AWS are designed for running high-performance computing workloads efficiently.
         - They offer optimized price-performance for scaling HPC tasks.
         - Ideal for applications requiring robust processing power, like complex simulations and deep learning tasks.
         - Suited for large-scale operations where performance is critical.
         - Tailored with high-performance processors to enhance computational capabilities.

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

## Amazon EC2 – Associate

## Amazon EC2 – Instance Storage
