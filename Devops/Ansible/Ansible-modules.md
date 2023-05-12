# ANSIBLE MODULES 
## System modules 
## Command modules: 
* Execute a command on a remote node 
## Script modeule:
* Use to copy script on a remote server 
## Service modules:
* used to manage services 
## Line in file module
* Used to search for a line and replace it or add it if it does not exit 
* 
## File modules 
## Database Modules 
## Cloud modules
## Windows modules 

# ANSIBLE VARIBALES 
vars:
    dns-servers: 10.0.0.1
-----
tasks:
    line : nameserver '{{dns-servers}}'

* No apostrophe when the varible is in a sentence 


# CONDITIONAL
WHEN 

# LOOPS 
 
 #