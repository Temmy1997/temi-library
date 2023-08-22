# EC2 Purchasing Option 

## Spot Instance 
1. Good for short workload 
2. Cheapest EC2 purchasing option
3. Less reliable (UYou can lose your EC2 instanc
4. 

## Dedicated Hosts 
1. Used for companies with strong compliance needs
2. Used for software that have complicated licensing models. 
3. Most expensive EC2 Purchasing Option available.

## Security Group 
* Used to control traffic in and out of EC2 instances
* Security Groups can be attached to multiple EC2 instances within the same AWS Region/VPC.

## EC2 Reserved Instances
1. it can be reserved for 1 or 3 years 
2. Reserved Instances are good for long workloads. You can reserve EC2 instances for 1 or 3 years.

## Compute Optimized 
Compute Optimized EC2 instances are great for compute-intensive workloads requiring high-performance processors (e.g., batch processing, media transcoding, high-performance computing, scientific modeling & machine learning, and dedicated gaming servers).

## Storage Optimized 
* EC2 instances are great for workloads requiring high, sequential read/write access to large data sets on local storage.
* Handle this high-frequency OLTP database

## Memory Optimized
EC2 instances are great for workloads requiring large data sets in memory.

## Spot Fleet 
1. Spot Fleet is a set of Spot Instances and optionally On-demand Instances.
2. It allows you to automatically request Spot Instances with the lowest price.

## Elastic Network Interfaces (ENIs) 
* Bounded to a specific AZ. 
* You can not attach an ENI to an EC2 instance in a different AZ.

## EC2 Hibernate
* To enable EC2 Hibernate, the EC2 Instance Root Volume type must be an EBS volume
* Must be encrypted to ensure the protection of sensitive content.

# EC2 Placement Group 

## Cluster Placement Groups 
* Place your EC2 instances next to each other which gives you high-performance computing and networking.

## Spread Placement Group 
* places your EC2 instances on different physical hardware across different AZs.