
### What is Amazon Athena

Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL queries. Athena is serverless, so there is no infrastructure to setup or manage, and you can start analyzing data immediately. You don’t even need to load your data into Athena, it works directly with data stored in any S3 storage class. 

To get started, just log into the Athena Management Console, define your schema, and start querying. Amazon Athena uses Presto with full standard SQL support and works with a variety of standard data formats, including CSV, JSON, ORC, Apache Parquet and Avro. 

While Athena is ideal for quick, ad-hoc querying and integrates with Amazon QuickSight for easy visualization, it can also handle complex analysis, including large joins, window functions, and arrays. 

## July-29-2018

### NAT vs Bastions

* A NAT is used to provide internet traffic to EC2 instances in private subnets

* A Bastion is used to securely administer EC2 instances  (using SSH or RDP) in private subnets. 


### VPC/Subnets points to remember

* [VPC-Subnets](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html#vpc-subnet-basics)
* A VPC spans all AZs in the region.
* There can only be 5 VPCs per REGION. A region has a minimum of 3 AZs. 
* A Subnet is created within a VPC and is assigned a unique ID. 
* A Subnet cannot span across AZ. A subnet is always within a AZ. 
* A Subnet becomes public when its traffic is routed through an Internet Gateway. 
* You can create a **flow log** on your VPC or subnet to capture the traffic that flows to and from the network interfaces in your VPC or subnet.
* AWS provides two features that you can use to increase security in your VPC: security groups and network ACLs. 
  * Security groups control inbound and outbound traffic for your instances, and 
  * network ACLs control inbound and outbound traffic for your subnets.
* Each subnet must be associated with a route table, which specifies the allowed routes for outbound traffic leaving the subnet. Every subnet that you create is automatically associated with the main route table for the VPC.
* [VPC-Peering-Guide](https://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide/Welcome.html)
* A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network.

* [amazon-vpc-limits](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/amazon-vpc-limits.html)
* Block IP Address using NACL.
* When creating a NAT instance, Disable Source/Destination check on the instance.
* NAT instances must be in a public subnet.
* There must be a route out of the private subnet to the NAT instance in order for this to work.
* The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size. 
* Scaling NAT instance  - Create high availability using auto scaling groups, multiple subnets in different AZs and a script to automate failover.
* NAT instances are always behind a security group. 
* NAT Gateways are better than NAT instances

##### NAT Gateways

* Preferred by the Enterprise
* Scale automatically upto 10 GBPS.
* Automatically assigned PUBLIC IP address.
* More secure than NAT instances.



