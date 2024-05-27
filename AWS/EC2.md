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
