
### What is Amazon Athena

Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL queries. Athena is serverless, so there is no infrastructure to setup or manage, and you can start analyzing data immediately. You don’t even need to load your data into Athena, it works directly with data stored in any S3 storage class. 

To get started, just log into the Athena Management Console, define your schema, and start querying. Amazon Athena uses Presto with full standard SQL support and works with a variety of standard data formats, including CSV, JSON, ORC, Apache Parquet and Avro. 

While Athena is ideal for quick, ad-hoc querying and integrates with Amazon QuickSight for easy visualization, it can also handle complex analysis, including large joins, window functions, and arrays. 

## July-29-2018

### NAT vs Bastions

* A NAT is used to provide internet traffic to EC2 instances in private subnets

* A Bastion is used to securely administer EC2 instances  (using SSH or RDP) in private subnets. 


### VPC points to remember

* Block IP Address using NACL.
* When creating a NAT instance, Disable Source/Destination check on the instance
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



