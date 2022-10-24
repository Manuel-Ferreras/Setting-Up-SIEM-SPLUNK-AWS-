# SIEM-SPLUNK-AWS-

 Set up a Splunk server in a secure AWS ec2(Amazon Elastic Compute Cloud).
 
ec2 configuration 

- Ubuntu AMI from quick start
- Instance type t2.micro free tier eligible
- key pair-
  -  Key pair type = rsa
  -  privite key file format  pem for open shh use ( use to connect from my linux teminar) 
- networking-  
  -  Create security group(Firewall)  allow  shh traffic from only my public IP and port 22 for ssh.
  -  Only allow the port nunber splunk enviriment is going to run 
  - assing an assign an elastic ip so you aways have the same public ip if you shut down your ec2 (is better to have a dynamic ip address for security over comfort)
  
-  crated an Iam role and give user enough Permission use for my ec2 Splunk server - following The principle of least privilege
  
  Conneting to yor ec2
  
  what you need to before trying to connect to your ec2 in the shell enviment 
  
 change permmision in you in your ec2 key using chmod
 
 
  
  
  
  










