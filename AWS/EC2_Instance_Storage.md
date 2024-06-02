# 1. EBS Elastic block storage
- CCP (Certìied Cloud Practitioner) - one EBS can be only mounted to one EC2 instance
  - Associate level : multi-attach feature for some EBS
  - AZ : Availability Zone
  - EBS ~ one USB: 1 USB only 1 PC but 1 PC can be has 2 USB, same 1 EBS - 1 instance but 1 instance - more EBS 

# 2. AMI Amazon machine image

# 3. EFS Elastic File System
- Sync between two instance: /mnt/efs/fs1

# 4. Q & A
- EBS Volumes are created for a specific AZ. It is possible to migrate them between different AZs using EBS Snapshots.
- You have launched an EC2 instance with two EBS volumes, Root volume type and the other EBS volume type to store the data. A month later you are planning to terminate the EC2 instance. What's the default behavior that will happen to each EBS volume? => By default, the Root volume type will be deleted as its "Delete On Termination" attribute checked by default. Any other EBS volume types will not be deleted as its "Delete On Termination" attribute disabled by default.
- AMIs are built for a specific AWS Region, they're unique for each AWS Region. You can't launch an EC2 instance using an AMI in another AWS Region, but you can copy the AMI to the target AWS Region and then use it to create your EC2 instances.
- When creating EC2 instances, you can only use the following EBS volume types as boot volumes: gp2, gp3, io1, io2, and Magnetic (Standard).
- Using EBS Multi-Attach, you can attach the same EBS volume to multiple EC2 instances in the same AZ. Each EC2 instance has full read/write permissions.
- You would like to encrypt an unencrypted EBS volume attached to your EC2 instance. What should you do? => Create an EBS snapshot of your EBS volume. Copy the snapshot and tick the option to encrypt the copied snapshot. Then, use the encrypted snapshot to create a new EBS volume
- EFS is a network file system (NFS) that allows you to mount the same file system on EC2 instances that are in different AZs.
- EC2 Instance Store provides the best disk I/O performance.
- You are running a high-performance database that requires an IOPS of 310,000 for its underlying storage. What do you recommend? => You can run a database on an EC2 instance that uses an Instance Store, but you'll have a problem that the data will be lost if the EC2 instance is stopped (it can be restarted without problems). One solution is that you can set up a replication mechanism on another EC2 instance with an Instance Store to have a standby copy. Another solution is to set up backup mechanisms for your data. It's all up to you how you want to set up your architecture to validate your requirements. In this use case, it's around IOPS, so we have to choose an EC2 Instance Store.
  - 64,000 is the maximum IOPS you can achieve when you're using EBS io1 or io2 volume types.
  - 256,000 is the maximum IOPS you can achieve when you're using the EBS io2 Block Express volume type.
  - 16,000 is the maximum IOPS you can achieve when you're using the EBS gp2 volume type.
