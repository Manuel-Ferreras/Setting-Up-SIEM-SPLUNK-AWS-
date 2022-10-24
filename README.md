# SIEM-SPLUNK-AWS-

<h1> Set up a Splunk server in secure AWS ec2(Amazon Elastic Compute Cloud) by setting role,security group(Firewall),ssh rules, and securing  my privite key.<h1>
 
 <h2> ec2 configuration </h2>

- Ubuntu AMI from quick start                                                           
- Instance type t2.micro free tier eligible
- key pair
  -  Key pair type = rsa
  -  privite key file format  pem for open shh use ( use to connect from my linux teminar) 
- networking  
  -  Create security group(Firewall)  allow  shh traffic from only my public IP and port 22 for ssh.
  -  Only allow the port number splunk enviriment is going to run.
  - assing an assign an elastic IP so you aways have the same public IP if you shut down your ec2 (is better to have a dynamic IP address for security over comfort).
  
- created an IAM role and give users enough Permission to use my ec2 Splunk server - following The principle of least privilege.
  
 <h2> Conneting to yor ec2 </h2>
  
  what you need to before trying to connect to your ec2 in the shell enviment.
  
  - change permissions in you in your ec2 pair key using chmod because your key pair is unprotected  and it will not allow you to ssh into your ec2 with a weak permission. 
 
  <img src="https://i.imgur.com/vQUYDFL.png" height="40%" width="44%" alt=/> 
  
- Connect to my by you using this command shh -i (yourec2key) ec2-user@(youec2plublicip)
  
 <img src="https://i.imgur.com/aR7SMmb.png" height="40%" width="44%" alt=/> 
 
  <h2>Installing and configuring SPLUNK in a ec2</h2>
  
- You need to log in to your SPLUNK account and select the command line option to download. copy the Linux command and paste it into your terminal.

  <img src="https://i.imgur.com/2Gk6kNW.png" height="40%" width="44%" alt=/> 

- After downloading your file tar you download the file you use = Tar -xvzf (name of your download file)
- Next you got to start Splunk from your bin directory using (./splunk start) and set username and password.

Then I went to my Splunk address web server the is going to be HTTP://(your ec2 public IP):(your assing port).
  
  <img src="https://i.imgur.com/JdJgW33.png" height="40%" width="44%" alt=/> 
  
  - To make my Splunk web server start at boot you got to type this commands in your bin directory.
    - ./splunk enable boot-start
    - systemctl enable splunk
    - sysmtemctl start splunk


