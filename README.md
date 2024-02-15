# Aws Solutions Architect Associate Notes

> Click ⭐ if you like the project.

## Visit Document Website

https://aws-solutions-architect-associate-notes.vercel.app

### Table of Contents

| No. | Questions                                                   |
| --- | ----------------------------------------------------------- |
|     | **AWS**                                                     |
| 1   | [What is AWS?](#what-is-AWS)                                |
| 2   | [AWS Cloud Use Cases](#AWS-Cloud-Use-Cases)                 |
| 3   | [Global Services](#Global-Services)                         |
| 4   | [Region-scoped Services](#Region-scoped-Services)           |
|     | **AWS IAM (AWS Identity and Access Management)**            |
| 1   | [What is IAM?](#what-is-IAM)                                |
| 2   | [IAM features](#IAM-features)                               |
| 3   | [Accessing IAM](#Accessing-IAM)                             |
| 4   | [Users & Groups](#Users-&-Groups)                           |
| 5   | [Permissions](#Permissions)                                 |
| 6   | [Roles for Services](#Roles-for-Services)                   |
| 7   | [Permissions](#Permissions)                                 |
| 8   | [Security Tools](#Security-Tools)                           |
| 9   | [Guidelines & Best Practices](#Guidelines-&-Best-Practices) |
|     | **Amazon EC2 – Basics**                                     |
| 1   | [What is Amazon EC2?](#what-is-Amazon-EC2)                  |

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
     - Renting virtual machines (EC2)
     - Storing data on virtual drives (EBS)
     - Distributing load across machines (ELB)
     - Scaling the services using an auto-scaling group (ASG)

## Amazon EC2 – Associate

## Amazon EC2 – Instance Storage
