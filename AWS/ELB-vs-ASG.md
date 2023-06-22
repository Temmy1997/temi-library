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
4. Its is integratesd with many AWS  services (EC2, EEC2 Auto sclaing group, EC, Cloudwatch, Route 53, etc.)

## Health check 
1. THis is a way the ELB verify whether or not an EC2 instance is working properly.
2 Health check is done on aport and route. 
3. If the health check os not 200 (ok), the the instance is unhealthy. 

## Types of load balancers on AWS 
1. Classic Load Balancer (v1 - old genration) - 2009: AWS doees not wnat peoeple to use this load banalcer anymore. (It supports HTTP, HTTPS, TCP, SSL, Secure TCP) 
2. Application Load Balancer (v2 new generation) - 2016  (HTTP, HTTPS, WebSocket)
   * Allows to route eto muliple HTTP applications accross machine (target groups)
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