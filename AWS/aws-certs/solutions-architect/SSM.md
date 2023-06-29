# AWS SYSTEM MANAGER
System manager is a AWS services that manages resources inside AWS account (Like ec2 instance eith windows or linux)
* If the resource is an EC2 instance, we have to attach the SSM policy to a role and attach therole to the EC2 instance. 
* Latest EC2 AMI have SSM agent reconfigured or else we will have to install it on the server. 


## RUN COMMAND 
* Provide a way to execute task without ssh or rdp into the ec2 instance servers
* The tasks are = installing, configuring e.t.c 
## STATE MANAGER 
* Helps to define the state of instances 
# INVENTORY 

# PACTH MANAGER 

# PARAMETER 


# RUNNING ANASIBLE PLAYBOOK USING AWS SYSTEMS MANAGER
1. Create an IAM role with SSM  policy
2. Attach the IAM role to the two EC2 instances
   Note: Latest AMI for EC2 instance has an alreday installed SSM agent
   If the instance does not have, install the SSM agent on the EC2 instance
   To cheeck if you have the service run (systemctkl status amazon-ssm-agaent)
3. Check fleet manager under node management section in SSM for the EC2 iNSTANCES
4. Got to Statemanager in AWS system, manager 
5. Create an association
6. In other to run ansible playbook from Github or S3, you would have to choose AWS-RunRemoteScript Document. 
Note: AWS-RunRemoteScript Document: 
Execute scripts stored in a remote location. The following remote locations are currently supported: GitHub (public and private) and Amazon S3 (S3). The following script types are currently supported: #! support on Linux and file associations on Windows
