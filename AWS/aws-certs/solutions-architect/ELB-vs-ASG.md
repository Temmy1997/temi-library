# Elactic Load Balancing (ELB) 
* ELB are servers that forwards traffic to mutiple ec2 servers(instamces).
* It spread load across multiple downstream servers(Instances)
* Because load balancers does health checks, failure of downstream servers can be handled easily. 
* Health check are done regularly to all rhe instances. 
* It exposes  asingle point of access to to the application.
* HIghly availability accross zones.
* Provides SSL termiation (HTTPS) for websites.
  

## WHY USE ELB
1. ELB is a managed load balancer
2. AWS manages ELB 
3. It cost less to setup.
4. Its is integratesd with man y AWS  services (EC2, EEC2 Auto sclaing group, EC, Cloudwatch, Route 53, etc.)

## Health check 
1. THis is a way the ELB verify whether or not an EC2 instance is working properly.
2 Health check is done on aport and route. 
3. If the health check os not 200 (ok), the the instance is unhealthy. 

## Types of load balancers on AWS 
1. Classic Load Balancer (v1 - old genration) - 2009: AWS doees not wnat peoeple to use this load banalcer anymore. (It supports HTTP, HTTPS, TCP, SSL, Secure TCP) 
2. Application Load Balancer (v2 new generation) - 2016  (HTTP, HTTPS, WebSocket)
   * Allows to route to muliple HTTP applications accross machine (target groups)
   * Load balancing to multiple applications on the same machine (e.g container)
   * Routing table to different target groups
   * Fixed hostname (xxx.region.elb.amaaxonaws.com)
   * Application servers will not see the eip of the client direlty 
  
3. Network Load Balancer (v2 new generation) - 2017 (TCP, TLS, Secure TCP, UDP)
   * Layer 4 load balancer (tcp, udp)
   * It handles millions of requests per second
   * Less latency 
   * Has one static IP address per AZ. (Spport Elastic IP )
   * Its not included in the AWS free tier 
   * HeLTH CHECK SUPPORT (TCP, HTTP, HTTPS) 
   * All traffic goes trough the NLB in the security group 
  
4. Gateway Load Balancer (2020) - It operates atNetwork layer (lAYER 3) 
5. It basicall analyze the Gateway Load Balancer 
  * Use a Gateway load balancer when you want all traffic to pass through firewall, inntrusion, detection, inpection e.t.c before it reaches thje application 
  * pass the traffics from the User - route table - Target grop - Gateway Load Balancer - Application
  * It operates at the network layer 
  * It uses GENEVE Protocol on port 6081 
  * Target groups (It can be EC2 Instance or IP ADDRESS)


## CROSS-ZONE BALANCING 
1. With croass Zone Load Blanceer : Each load balancer instance ditribute traffic evenly accross all registed instances in AZ 

2. Without cross Zone load balancer: Requests are distributeed ib the einstnce eof the node eof the elactic load balancer. 

Application load balancer: 
* Cross-zone blanacing is emabled by default at the Taget group level.
* No charges for the innter AZ data 

Network Load Balancer
* Disbled by default 
* You have to pay to enable ithe cross zone balancer 

Classic Load Blancer 
* Disbaled by defult 
* You will not be charge if you  enable the cross zone load balancer.

## NOTE : The following cookie names are reserved by the ELB (AWSALB, AWSALBAPP, AWSALBTG).
## SSL/TLS 
* SSL Certificate allows traffic between CLIENT and load balancer to be encrpted in transit 
SSL: Secure Socket Layer 
TLS: Transport layer secuirty (Newer version of SSL) 
* SSL certificate has an expiration dates (You must renew) 
* The load balancer uses X.509 certificates
* AWS CERTIFIED MANAGER can be used to manage SSL certificates 
* You can also upload your own certificates alternativly. 

 ## SERVER NAME IDICTATION
 * It solves loading multiple SSL certificate onto one web sever in other for that web server to serve multiple website. 
 * It a nn,new protocol that requires client to indicate the hpstname of the target server in the initail SSL certificate. 
 * It onlu works when you use ALB /NLB 

# AUTO SCALING GROUP (ASG) 
* IT scales out{Add EC2 instance}
* It scales in {Remove EC2 INSTANCE}
* It akes sure we have a minimum and maximum number of eC2 instances RUNNING. 
* Automatically register new isnatnces to a load balancer 
* Re-create an EC2 INSTANCE in case the previos EC2 instance is tyerminated. 
* ASG is free in AWS 

## Attributes of ASG 
1. Launch template 
2. Min size / Max size capacity 
3. Scaling policies 

## Auto scaling with Cloud watch & SCALING
1. You can scale i & out in ASG using the cloud watch alarm. 
2. Alarm monitors the custom metrics or Average CPU 

## Auto scaling Groups -Scaling Policiees 
1. Dynamiic Scaling Pilicies 
* Target Tracking Scaling
   *   Most simple and easy to set up 
   *   Used to track the average CPU utilization  of any autoscaling group to stay like aroud 40% 
* Simple /Stp Scaling 
     * A cloudwatch alarm is triggered (Example: When CPU goes over 70% , add 2 instances) or {CPU is below 30& , then remove 1 instance}
* Scheduled Actions 
      * Anticipate a scaling based on the known uage pasttern 
2. Predictive sclaing 
   Continually having to forecast adn schedule scaling ahead 
   * Good metrics to scale on
         1. CPU Utilization
         2. Reques Count Per Target 
         3. 

