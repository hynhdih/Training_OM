# 1. AWS Budget setup
- Account -> Billing and Cost Management -> Budgets : Control budget 

# Notes:
- ***Stop instance***:  After you stop the instance, you are no longer charged usage or data transfer fees for it. However, **you will still be billed for associated resources, such as attached EBS volumes and associated Elastic IP addresses**.
- If you stop an instance and then you start it later on, then AWS will maybe change its public IPv4. But, The private IP will always stay the same.

# 2. EC2
- EC2 = Elastic Compute Cloud = Infrastructure as a Service
-  It mainly consists in the capability of :
  - Renting virtual machines (EC2)
  - Storing data on virtual drives (EBS)
  - Distributing load across machines (ELB)
  - Scaling the ser vices using an auto-scaling group (ASG)

# 3. EC2 Instance types
- Can use different types of EC2 instances that are optimised for different use cases (https://aws.amazon.com/ec2/instance-types/)
-  AWS has the following naming convention: m5.2xlarge
  -  m: instance class
  -  5: generation (AWS improves them over time)
  -  2xlarge: size within the instance class
  -  Ví dụ: t2.micro
# 4. Security groups and Classic ports
- the inbound rules are the rules that allows connectivity from the outside into the EC2 instance.
- outbound: allow all traffic on IPv4 to anywhere, allows our EC2 instance to get full internet connectivity anywhere
# 5. Q & A
- Spot Instances are good for short workloads and this is the cheapest EC2 Purchasing Option. But, they are less reliable because you can lose your EC2 instance. Althought It provide you the biggest discount, but it is not suitable for critical jobs or databases
- Security Groups operate at the EC2 instance level and can control traffic
- EC2 Reserved Instances can be reserved for 1 or 3 years only.
- Memory Optimized EC2 instances are great for workloads requiring large data sets in memory
- General Purpose EC2 instances are great for a diversity of workloads that require a balance between computing, memory, and network.
- Storage Optimized EC2 instances are great for workloads requiring high, sequential read/write access to large data sets on local storage.
- Compute Optimized EC2 instances are great for compute-intensive workloads requiring high-performance processors (e.g., batch processing, media transcoding, high-performance computing, scientific modeling & machine learning, and dedicated gaming servers).
- On-demand Instances are good for short workloads with predictable pricing.
- Reserved Instances are good for long workloads. You can reserve EC2 instances for 1 or 3 years.

- You are preparing to launch an application that will be hosted on a set of EC2 instances. This application needs some software installation and some OS packages need to be updated during the first launch. What is the best way to achieve this when you launch the EC2 instances? : EC2 User Data is used to bootstrap your EC2 instances using a bash script. This script can contain commands such as installing software/packages, download files from the Internet, or anything you want.

- Security Groups can be attached to multiple EC2 instances within the same AWS Region/VPC.

- You're planning to migrate on-premises applications to AWS. Your company has strict compliance requirements that require your applications to run on dedicated servers. You also need to use your own server-bound software license to reduce costs. Which EC2 Purchasing Option is suitable for you? : Dedicated Hosts are good for companies with strong compliance needs or for software that have complicated licensing models. This is the most expensive EC2 Purchasing Option available.

- You would like to deploy a database technology on an EC2 instance and the vendor license bills you based on the physical cores and underlying network socket visibility. Which EC2 Purchasing Option allows you to get visibility into them? => Dedicated Hosts

- Spot Fleet is a set of Spot Instances and optionally On-demand Instances. It allows you to automatically request Spot Instances with the lowest price.
