This document tells about AWS cloud computing and the various services and its characteristics

- [AWS Overview](#aws-overview)
  - [1.1 What is cloud computing ?](#11-what-is-cloud-computing-)
  - [1.2 Regions](#12-regions)
  - [1.3 Availability zone](#13-availability-zone)
  - [1.4 Edge location](#14-edge-location)
  - [1.5 Scope of services](#15-scope-of-services)
  - [1.6 AWS Features](#16-aws-features)
  - [1.7 Products of AWS](#17-products-of-aws)
    - [1.7.1 Compute in AWS](#171-compute-in-aws)
    - [1.7.2 Storage in AWS](#172-storage-in-aws)
    - [1.7.3 Database in AWS](#173-database-in-aws)
    - [1.7.4 Developer tools in AWS](#174-developer-tools-in-aws)
    - [1.7.5 Management tools in AWS](#175-management-tools-in-aws)
    - [1.7.6 Network & Content Delivery in AWS](#176-network--content-delivery-in-aws)
    - [1.7.7 Security, Identity, and compliance in AWS](#177-security-identity-and-compliance-in-aws)
    - [1.7.8 Messaging in AWS](#178-messaging-in-aws)
    - [1.7.9 Application Services in AWS](#179-application-services-in-aws)
    - [1.8.0 Mobile Services in AWS](#180-mobile-services-in-aws)
- [2 Identity Managment.](#2-identity-managment)
  - [2.1 IAM Overview](#21-iam-overview)
  - [3 Networking AWS](#3-networking-aws)
    - [3.1 VPC](#31-vpc)
    - [3.2 Sub Nets](#32-sub-nets)
  - [4 Routing](#4-routing)
  - [7 Network Access Control Lists (NACL)](#7-network-access-control-lists-nacl)
    - [NACL Summary](#nacl-summary)
  - [Security Group](#security-group)
  - [VPC Peering](#vpc-peering)
  - [VPN Access](#vpn-access)
  - [Amazon Elastic Cloud Computing (EC2)](#amazon-elastic-cloud-computing-ec2)
    - [2.1 Amazon Machine Image (AMI)](#21-amazon-machine-image-ami)
    - [2.2 Key Pairs](#22-key-pairs)
  - [Getting started with AWS](#getting-started-with-aws)
    - [Steps to create Network](#steps-to-create-network)
# AWS Overview 
## 1.1 What is cloud computing ? 
Cloud computing is internet based computing that provides shared computer processing resources and data to computers and other 
devices on demand. 

Characteristics
- `On-Demand self-service` Sign Up and enjoy the services without delays.
- `Broad Network Access` the resources that we have within the cloud can communicate with each other across the network through internet and in multiple channels (desktop, mobile, laptop e.t.c)
- `Resource pooling` Resources are pooled to multiple customers.
- `Rapid Elastic` - Ability to meet with demands quickly
- `Measured service` we pay for what we use 

Category 

 `1.Infrastructure as a Service:` Which allows you to easily provision the IT components you require; including networking capabilities, computers, multi-tenant or dedicated, and data storage.
 
 It's flexible and allows you to control and manage your IT resources similar to the way you would in a traditional on-premises data center, such as `EC2, S3, and VPC`.

`2.Platform as a Service:` It frees you from having to manage the underlying infrastructure and focus on the deployment and management of your application. 

It frees you from having to think about resource procurement, capacity planning, software maintenance, and patching. Examples of Platform as a Service on AWS include `Route 53, Elastic Load Balancing, and Auto Scaling`.

`3.Software as a Service:` It provides you with an application that is run and managed entirely by a service provider. Think of SaaS as an end-user application running in the cloud.

 In a SaaS environment, you have access to the capabilities of an application without the hassle of how it's maintained or its underlying infrastructure


## 1.2 Regions
 Within AWS have a number of regions all over the world, and regions are sort of the primary building blocks of AWS. 
 Some regions are Us-ohio, 
 ## 1.3 Availability zone
 With in region there are multiple data centers to choose from, and those are called availability zones. A availabilty zone can have one ore more data centers. 
 Severe data faults can be avoid by deploying the virtual machines in different availability zones.
 We can load balance across these availability zones and take advantage of that high-speed private fiber in order to greatly increase the fault tolerance, durability, and availability of our own applications.
## 1.4 Edge location
edge locations within AWS power several different services, namely Amazon Cloud Front, which gives us a content delivery network, Route 53, which gives us a global DNS service, and API Gateway, which gives us serverless REST APIs

 When we need to fulfill a DNS query, we want to fulfill that as quickly as possible with the lowest latency. And so, by having DNS servers running in edge locations all over the world, this allows us to respond to DNS queries with the lowest latency as well.
## 1.5 Scope of services
`Global Services` - changes are available across the regions 
    - AWS IAM 
    - Amazon Cloud Front

`Core services` include networking, compute, storage, and databases

`Application services` include SNS, SQS, and SWF

`Deployment and management services` include Elastic Beanstalk and Cloud formation.    

`Regional Services` - When we create a table within DynamoDB, that table and the data, and the requests that we make against that table are handled within one particular Region, whichever Region we happen to choose

 when a load balancer exists within one Region, allowing us to load balance across the data centers that are in that Region

- Amazon Dynamo DB
- Amazon Simple Storage Service(S3)
- Elastic load balancing
- Amazon Virtual Private Cloud

Availability zone
when we create certain resources those resources existis within a single Availability Zone.

When we launch EC2 instances, those exist in a single Availability Zone. When we divide our VPCs, our networks, into subnets, each subnet will also exist in a single Availability Zone
- Amazone Elastich Block Store (EBS)
- Amazon Elastic Cloud computing (EC2)
- Subnets

## 1.6 AWS Features
AWS offers numerous ways to create and manage resources. Following are the different ways to access the features offered by AWS.

`AWS Management Console` - A web interface for AWS.

`AWS Command Line Interface (AWS CLI)` - Commands for a wide set of AWS products.

***Command Line Tools***- Commands for individual AWS products.

`AWS Software Development Kits (SDK)` - APIs that are specific to programming language or platform.

`Query APIs` - Low-level APIs that are accessible using HTTP requests.

## 1.7 Products of AWS

### 1.7.1 Compute in AWS
Provides several compute products that allow to deploy, run, and scale applicationa as virtual servers, code or containers.

Different compute services offered by AWS

- Amazon EC2 - Virtual Servers in the Cloud
- Amazon EC2 Container Service - Run and Manage Docker Containers
- AWS Lambda - Run Code in Response to Events
- Amazon EC2 Container Registry - Store and Retrieve Docker Images
- Amazon Lightsail - Launch and Manage Virtual Private Servers
- Amazon VPC - Isolated Cloud Resources
- AWS Batch - Run Batch Jobs at Any Scale
- AWS Elastic Beanstalk - Run and Manage Web Apps
- Auto Scaling - Automatic Elasticity
- Lightsail Building Blocks.
   - usecase: "Infrastructure Lite", Simple web applications, Dev sandbox, POC
   - no prerequests
   - Parameters: 
        - Optional: Region, Availability Zone, Userdata, Keypair
        - Required: OS choice, Blueprint OS with/without software on top, Instance Plan (CPU and memory), Name + Tags



`Amazon EC2` offers resizable cloud-based compute capability taking shape as virtual servers. There are a broad range of instance types that are easily manageable and exhibit different combinations of networking capacity, storage size, amount of memory, and CPU power.

`Amazon ECS` is a scalable, performance container management service that allows to run and manage distributed applications. It Allows to schedule, launch and run Docker containers across a cluster of EC2 instance using a simple set of APIS. 

You can build and package the application in a docker container and seemlessly deploy the applications in to the production using EC2 container service. EC2 container service manages a cluster of Amazon EC2 instances and takes care of the state of the cluster as well scheduling, running and monitoring containers across your cluster.

- Mix of applications can be run across the clusters. For example a web-app and image processing app. It also monitors the clusters and reports how much of resources being used by each application and how much is left for new tasks. 
- It allows to quickly update or rollback containers regardless of 1 or 1000 containers. It makes it easy to run all the different task that make up your application such as web servers, queues, databases, API backends and background workers.
- Accessibly from AWS managenment console and AWS SDK's
- No additional charges for using EC2 container service. 

`Amazon Lambda` AWS Lambda aims to run code without managing or provisioning servers. It is a compute service that runs your backend code in response to the event such as uploading images to S3 bucket, updates to Dynamo DB and to Kinesis stream or in app activity. 

Once the code is uploaded to Lambda. It handles all the capacitiy, scaling, patching and administration of infrastructure to run your code. It also provide visibility of the performance by publishing the real time metrics log in to the Amazon cloud watch.

Code you run in AWS lambda is called AWS function. 
A low fees is charged per transaction and charges for the processing time of the lambda functions.

### 1.7.2 Storage in AWS
Cloud storage is more secure, scalable and reliable than on-premises storage. 
It gives wide varity of storage like Backup and archive, Databases, IOT and Big Data analytics depend on the data storage architecture.

`Amazon S3` is a object storage service which stores any quantity of data form anywhere in the intertnet. Objects stored in AWS S3 are secure, and incredible durability. 
Once data in saved s3, it can be tiered automatically into minimal cost, long-term cloud storage class like `Amazon Glacier` and `S3 standard - Infrequent Access` for archiving. 

Create a bucket in a region and pay only for buckets you are using. Data's stored in S3 buckets are version controlled and reduantly storing the data in multiple device and in multiple facilities.

`Amazon Glacier` is  an extremly low cost, secure and durable storage service for long-term data archiving and backup. 
Amazon Glacier offers three choices to access archives for a few minutes to numerous hours

`Amazon Elastic File System (AWS EFS)` is a shared file system for used with  AWS EC2. 
- Storage capacity is elastic i.e. that shrinks or grows automatically.
- Several Amazon EC2 instances can access an Amazon EFS file system simultaneously, letting Amazon EFS to offer a common data source for workloads as well as applications operating on more than one Amazon EC2 instance.
- Can be created from AWS SDF, CLI, and managment console. User permission can be granded to directory, file level using I AM policy.

### 1.7.3 Database in AWS

 - `Amazon Relational Database Service (Amazon RDS)` - supporting six widely used database engines
 - `Amazon DynamoDB` - a quick and flexible NoSQL database service,
 - `Amazon Aurora` - a MySQL-compatible relational database that delivers five times the performance
-  `Amazon Elasticache` - an in-memory cache service with Memcached and Redis support.
-  `Amazon Redshift` - a petabyte-scale data warehouse service.

`Amazon RDS` is very easy to set up, run, and scale a relational database in the cloud.

- offers resizable and low-cost capacity while managing database administration tasks that consume more time,
- Amazon RDS offers six similar database engines to select from, including Microsoft SQL Server, Oracle, MariaDB, Amazon Aurora, MySQL, and PostgreSQL.

`Amazon DynamoDB`  is a flexible and quick NoSQL database service for all applications that require single-digit, consistent millisecond latency at any scale.

- Completely cloud managed database, supporting document and key-value store models.

- reliable performance and flexible data model makes it suitable for several applications such as IoT, mobile, ad tech, web, and gaming.

 `According to Forrester, Amazon DynamoDB is the most popular NoSQL cloud database.`

### 1.7.4 Developer tools in AWS 

`AWS Code build`

    A build service that is fully managed, compiles source code, operates tests, and creates deployable software packages.

    CodeBuild scales endlessly and processes several builds simultaneously, so the builds are not in queue.


    Benefits

        Secure
        Allows Continuous Integration and Delivery
        Extensible
        Pay as You Go
        Continuous Scaling
        Fully Managed Build Service

### 1.7.5 Management tools in AWS 
- `Amazon EC2 Systems Manager:` Configure and Manage EC2 Instances and On-premises Servers
- `AWS CloudTrail:` Track User Activity and API Usage
- `AWS Config:` Track Resource Inventory and Changes
- `AWS Service Catalog:` Create and Use Standardized Products
- `AWS Personal Health Dashboard:` Personalized view of AWS service health
- `AWS CloudWatch:` Monitor Resources and Applications
- `AWS Cloud Formation:` Create and Manage Resources with Templates
- `AWS OpsWorks:` Automate Operations with Chef
- `AWS Trusted Advisor:` Optimize Performance and Securit

`Amazon Cloud watch` is a monitoring service designed for AWS cloud resources and the applications operate on AWS. Amazon CloudWatch can be used to:

    Automatically react to changes in AWS resources.
    Collect, monitor log files and set alarms
    Collect and track metrics

Attain system-wide visibility into `operational health, application performance, and resource utilization.`

Amazon CloudWatch monitors AWS resources such as

- Amazon RDS DB instances
- Amazon DynamoDB tables
- Amazon EC2 instances
- Custom metrics or logs created by services and applications

`AWS CloudTrail` is a service that allows risk auditing, operational auditing, compliance, and governance of AWS account.

- **Routinely monitor and retain events** specific to API calls throughout the AWS infrastructure.
- **Offers history of AWS API calls** for your account, which includes API calls done through the AWS SDKs, AWS Management Console, command line tools, and various AWS services.
- Reduces troubleshooting, security analysis, and resource change tracking.

Benefits:

- Security Automation
- Visibility Into User and Resource Activity
- Security Analysis and Troubleshooting
- Simplified Compliance

### 1.7.6 Network & Content Delivery in AWS 
Services offered -

- `Elastic Load Balancing:` High Scale Load Balancing
- `Amazon Route 53:` Scalable Domain Name System
    - Use case: DNS server
    - Resource creation: Domain registration, Record creation, health check creation.
    - Operation Summary: Domain renewal, Zone creation, Record create/updates, Health check mgmt.




- `Amazon Cloud Front:` Global Content Delivery Network
- `AWS Direct Connect:` Dedicated Network Connection to AWS
- `Amazon VPC:` Isolated Cloud Resources

### 1.7.7 Security, Identity, and compliance in AWS 
**Amazon Inspector** - automated security assessment service, that aids to enhance the compliance and security of applications deployed on AWS.

**AWS Identity and Access Management (IAM)** - controls users access to AWS services. Allows to create, manage users and groups, and deny or grant access.

**AWS Artifact** - the portal offers on-demand access to AWS compliance and security documents (audit artifacts).

**Amazon Cloud Directory** - set up flexible cloud-native directories to organize hierarchies of data along numerous dimensions.

**AWS Certificate Manager** - seemlessly manage, provision, and deploy Secure Sockets Layer (SSL)/Transport Layer Security (TLS) certificates.

**AWS CloudHSM** - fulfill regulatory, contractual and corporate compliance requirements for data security by utilizing dedicated Hardware Security Module (HSM). AWS Directory Service - allows AWS resources and directory-aware workloads to utilize managed Active Directory in AWS Cloud for Microsoft Active Directory.

**AWS WAF** - web application firewall that aids in protecting web applications from web threats that could eat up excessive resources, or compromise security, hinder application availability.

### 1.7.8 Messaging in AWS 

-    Simple Email Service (SES) - Email Sending and Receiving
-    Pinpoint - Push Notifications for Mobile Applications
-    Simple Notification Service (SNS) - Pub or Sub, Mobile Push and SMS
-    Simple Queue Service (SQS) - Managed Message Queues

### 1.7.9 Application Services in AWS 
- `AWS Step Functions` makes it easy to coordinate the components of distributed applications and microservices using visual workflows. Building applications from individual components that each perform a discrete function lets you scale and change applications quickly.
(e.g) Build state machine - processing order by running one more lambda function and orchestrating them using step functions.
- `Amazon API Gateway` is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. It offers a comprehensive platform for API management. 

Amazon API Gateway allows you to process hundreds of thousands of concurrent API calls, including traffic management, authorization and access control, monitoring, and API version management.

Pay only for the API calls received and the data transferred.

### 1.8.0 Mobile Services in AWS 

-  AWS Mobile Hub - provides a integration console and offer provisions and configures to AWS service to Build, Test, and Monitor Apps
-  Amazon Cognito - User Identity and App Data Synchronization. This functions both offline and online, and enables to store user preferences securely such as Game state, and application preferences, also works with several existing identity providers.
-  AWS Mobile SDK - Mobile Software Development Kit
-  Amazon API Gateway - Build, Deploy, and Manage APIs
-  Amazon Pinpoint - Push Notifications for Mobile Apps
-  AWS Device Farm - Test Android, FireOS, and iOS Apps on Real Devices in the Cloud




# 2 Identity Managment.

## 2.1 IAM Overview
The IAM service is concerned with authentication and authorization to the AWS API, and within that service we can create users, we can create groups of users, we can also create a number of other mechanisms, we can enforce a password policy, we can enable and enforce multifactor authentication using a six digit pin, and within the IAM service

AWS API Service (Access ID + Secret key)
Using this api we can do the following 
- Authentication
- Authorization
- Users
- Groups
- Password policy
- Multi-factor authentication

> Note: Other EC2 instance's operating system and Application layers will have their own authentication and authorization </br>
CLI, SDKs and Management Console are the client of the AWS API using this you can create resource with in AWS.


## 3 Networking AWS

### 3.1 VPC 

With Amazon VPC, we have the ability to create logically isolated networks. So, on premises, you have your network. The internet is its own network, and those two networks, by default, are isolated from one another until you put something in place that allows them to communicate, and VPCs are the same way, so if I create my VPC and you create your VPC, those are two completely different networks that remain completely isolated from one another

VPC's are create per account per region, and it spans the entire region, but it can make use of all of the availability zones in that region. 

Using security mechanism you can peer VPC with in the region to communicate directly, and also peer between VPC's in multiple region.

We also have the ability to create gateways. Gateways are a device that allows one network to communicate with another network, and so, if we wanted to communicate with the internet, then we would create and attach an internet gateway. If we wanted to communicate with on-premises through a VPN, then we would create a VPN gateway. Now, keep in mind that, with most Amazon services, there are limits. 

There are hard limits which are due to limitation with the technology itself and soft limits are really put there by AWS to help control resource consumption. 

parameter: CIDR RANGE (e.g) 10.0.0.0/16


### 3.2 Sub Nets

With only VPC we can't do anything for every Amazon resource to be deployed and run we need subnets. 

Next thing is VPC into subnets. Subnets are, as the name suggests, a subdivision of a network, and so it's a way of isolating different parts of our network to create, perhaps, functional placement of different devices for different purposes, and to create isolation for security. And so, subnets within Amazon VPC perform two primary, very important functions. 

One is to create isolation between tiers, so if you're designing a multi-tier system, then every subnet, perhaps every tier, would get its own subnet, so that you can have that isolation between tiers, and so, here, we might have a subnet that can be routed to the internet, and we might have a second subnet in a second availability zone, also routed to the internet, and so the other thing that a subnet does is to map, give us a physical mapping, to an availability zone. When we create subnets, they are created specifically one to one with an availability zone, and so we have isolation between tiers and a mapping to an availability zone

Launcing Ec2 instance in two different subnets in two different availabilty zone provides resilient if once system/datacenter is down then another can backup. We can have public subnets which is exposed to internet and private networks too.

## 4 Routing 
- Routing is concerned with the flow of traffic. 
- Routing is not concerned with protocols and ports, not concetrned with 
TCP versus UVP, port 22 vs port 443. 
- Its only concerned about whether or not any all traffic can move. 
- Once routing in place we can filter the traffic based on the protocol and port so on. 
  
## 7 Network Access Control Lists (NACL)
### NACL Summary 
- Firewall for the subnet as a whole
- Stateless:  It just sees a network packet either coming in or going out and it doesn't correlate responses with requests, and its the reason for specifying ingres and egress rules.

- Rules applied in order :  we had rules, specified at rule 100, rule 110, and so on, and rules are matched in the order that they're specified in that table
- Must specify ingress and egress
- May specify allow or deny rules
- Default NACL allows all ingress/egress

## Security Group

 - Security Groups are firewalls that are applied to individual instances or other devices like load balancers.

 - Security groups are stateful, which means that they do recognize responses as being responses to a request that was allowed to come in to begin with. so you'll notice here in our Egress Rules, we are not specifying the ephemeral port range because we don't need to
 
 - when you create a VPC, several things are also created at the same time such as a default security group. With a default security group, all ingress traffic is denied, but all egress traffic is allowed. 


## VPC Peering
- Connections between two VPCs
- Always one-to-one
- No transitive peering
- Helps to segregate network
- No bottleneck or SPOF
- IP ranges must not overlap
- No edge-to-edge routing 

we can peer VPCs that are in the same region or we can peer VPCs that are in different regions. We can peer VPCs in the same account or across different accounts.

Scenarios:
1. Creating a separate VPC for each tier like (web, backend, Database) and all this VPC communicating through the VPC peering connection

2. VPC peering for VPC created per department like (Payment and Revenue Accounting)

3. Centalized Resources
VPC Intranet/File sharing in one VPC and might want to provide access to   VPC dept, VPC customer, VPC vendor

> Note: If you look at this solution like this provides you with the security you need, the trade-off is that you're going to pay for that in terms of the VPC pairing connection charging that bandwidth
 
## VPN Access
- VPN provides secure way of connection between Amazon VPC and application running on-premises.
- We can establish this connection through VPN gateway it provides IPsec encryption.
- when we create a VPC tunnel with this VPN gateway, we actually get for every VPN connection we actually get two tunnels, right? And so, we have our VPN gateway on the Amazon side, we have our customer gateway on-premises, or in a remote location somewhere. And so the customer gateway could be a physical device like a Cisco ASA or a Palo Alto, or it could be a virtual device
- Once the routes are in place, here, what we're looking at is what we call a propagated route. We can configure routing on the actual VPN connections, and whatever routing we configure here, whether it be dynamic or static, those routes can be what we call propagated to the route table for us. And so once that route, you'll see here perhaps, for example, routing 192.168.0.0/16, that would then allow by directional communication between our VPC and some remote location over IPsec encrypted communication 

## Amazon Elastic Cloud Computing (EC2)
- Virtual machines(instance)
- Your choice of Linux or Windows
- Xen or Nitro hypervisor
- Bare metal is available
- Combinations of CPU, memory, disk, IO
- Launch one to thousands*
- Different billing models
- Hourley fee includes OS license.
- Per seconds fee available for certain OS
- AWS Marketplace offers canned solutions like Bigdata solutions.

### 2.1 Amazon Machine Image (AMI)
- Bit-for-bit copy of root volumns
- Choice of OS
    - Windows
    - Linux
    - FreeBSD
- Find AMIs:
    - AWS-provided
    - Trusted publishers
    - Community
    - AWS Marketplace to find canned solutions

Launching an instance
 *[HTML]: <table border="1">
            <tr><td>1. Chooose AMI </td><td>2. Launch instance</br>
            Install and Config e.t.c </td><td>1.  3. Create a private image</td><tr>
          </table>  
   
### 2.2 Key Pairs
- Public and private keys (local)
- These are 2048-bit SSH-2 RSA keys
- Create key pair
    - In AWS
    - Local and import public key to AWS
- AWS keeps public key
- AWS does not keep private key. 
- Choose key pair when launching EC2 instance, That  will allow us to gain remote access to that instance 

**Linux**
- Public key added to .ssh/authorized_keys
- Use private key for SSH login

**Windows**
- Administrator password encrypted by AWS 
- Use the private key to decryption.

## Getting started with AWS

### Steps to create Network 
Go to a region (e.g) Frankfurt
1. Create a VPC with CIDR RANGE (e.g) 10.0.0.0/16 
2. Create an public subnet -> select VPC, Availability zone, CIDR Range (e.g) 10.0.1.0/24 (subnet of the VPC CIDR range)
3. Create an private subnet -> select VPC, Availability zone, CIDR Range (e.g) 10.0.2.0/24 (subnet of the VPC CIDR range)
4. Create internet gateway(igw), and then attached to VPC 
5. Create a route table (e.g) rt-public //To allow traffic to and from from internet.
    i) Add a route table entry 0.0.0.0/0 target -> igw
    ii) Add subnet associations to the public subnet 
6. Create NAT Gateway 
A nat gateway is deployed in to an public subnet and has to have an elastick ip address. its a paid service. It allows 
outbound traffic from the private subnet to the public, but not inbound connection request. 
Create a NAT gateway (nat-gw) -> select public subnet, create EIP
 Create a private route table
   i) Add a route table entry  0.0.0.0/0 target -> nat-gw
   ii) Add subnet association to the private subnet.
Note: Until 5 everything is free, only NAT Gateway is chargeable   

Tool to build a secure cloud, Use this tool to create VPC and other services.
https://asecure.cloud/p/securevpc/ 

https://www.ec2instances.info/   To filter and ec2 instances




   



    


