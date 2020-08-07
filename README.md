# AWS Developer Associate Prep

Following are the contents for the AWS Developer Associate Preparation

## Setting up Budget
1. click on profile drop down on top right corner
2. Go to My Billing Dashboard
3. on Left Pane under Cost Management, click on Budget
4. Create a Budget, select cost budget
5. Configure Alert to add your email, then create budget

## AWS REGIONS
1. A region is a cluster of data centers
2. AWS services are Region Scoped

## AWS AVAILABILITY ZONES (AZ)
1. Each region has many availability zones
2. minimum is 2, usually 3
3. Each AZ is one or more discrete data centers with redundant power, networking and connectivity

## Global Service VS Region scoped service
1. EC2 is region specific
2. IAM is global service
3. AWS Global Infrastructure - https://aws.amazon.com/about-aws/global-infrastructure/

## IAM
1. root user, IAM user
2. users, groups and roles
3. policies are written in Json, policies define what users, group and roles can or cannot do
4. MFA
5. IAM has predefined managed policies
6. LEAST PRIVILEGED PRINCIPLE - allow permissions which are necessary only
7. IAM FEDERATION
8. ONE IAM USER PER PERSON, ONE IAM ROLE PER APPLICATION, IAM CREDS SHOULD NEVER BE SHARED, NEVER WRITE IAM CREDENTIALS IN CODE
9. Go to IAM dashboard and follow the steps of setting up MFA for root user, then setting up a group with policies, creating admin user, adding IAM admin to group, setting up password policy

## EC2
1. Launching virtual machines on cloud
2. comprises of EC2, EBS , ELB, ASG
3. Start , stop and terminate instance
4. AMI - Amazon machine image, Amazon Linux 2
5. type of machine - processing power, memory and storage
6. Tags are key value pairs to identify instances
7. when you try to connect to EC2 through SSH for the very first time using the PEM file will generate permissions 0644 error.
8. use chmod 0400 on the pem file then use it
9. ssh -i <ec2-instance-file.pem> ec2-user@ip
10. Following article is for chmod command https://www.cyberciti.biz/faq/unix-linux-bsd-chmod-numeric-permissions-notation-command/
11. chmod 0000 <fileName> , 1st 0 is for setuid, setgid , sticky bits; 2nd 0 is for owner; 3rd 0 is for group; 4th 0 is for others
12. https://linuxconfig.org/how-to-use-special-permissions-the-setuid-setgid-and-sticky-bits
13. ssh -i ./Downloads/EC2tutorial.pem ec2-user@3.17.145.91
14. when you stop your ec2 instance and start it back up, the public ip changes
15. EC2 instance connect is browser based terminal
16. in order to be able to connect to EC2 instance through SSH, you need to edit inbound rule in security group associated with it and add SSH on port 22

## Security Groups
1. They control how traffic will be allowed to EC2 instance
2. Security groups are categorized as inbound and outbound rules
3. it's better to maintain one security group for each type of connections.
4. By Default all inbound traffics are blocked and outbound traffics are authorized
5. if you have multiple EC2 instances attached to same security groups, they can communicate with each other by referencing the same security group

## Private and Public IP
1. IPV4 - 
2. IPV6 - 
3. Private IPs are within the private network
4. 5 Elastic IPs in your account can be allowed by default by amazon, if required you can ask for more.
5. If you assign an Elastic IP to an instance, it will retain the IP through stop and start of the instance.
6. If you create an elastic Ip and keep it unused then you would be charged for it

