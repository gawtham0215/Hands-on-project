<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Launching VPC Resources

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a virtual network that you can launch AWS resources in a logically isolated virtual network that you have defined.VPC gives you control over your network configuration IP address ranges, subnets, routing, and security settings.

### How I used Amazon VPC in this project

I use Amazon VPC in today's project to create my own VPC with different resources/components (e.g security groups, network ACLs), private resources (e.g a private subnet) and EC2 instances in both my private and public subnets.

### One thing I didn't expect in this project was...

The one thing you didn't expect in this project is advanced settings in VPC.

### This project took me...

The time I took to complete this project is 2 hours including documentation.

---

## Setting Up Direct VM Access

Directly accessing a virtual machine means "logging into" the EC2 instance (instead of just managing it to a higher level with the AWS Management Console). This includes installing and changing EC2 instance's configurations.

### SSH is a key method for directly accessing a VM

SSH traffic means Secure Shell and it is both a protocol and traffic type. It is the protocol that matches key pairs, and once the connection is setup, it is a traffic type that encrypts communication/data being transferred. 

### To enable direct access, I set up key pairs

Key pairs are tools that help engineers to authenticate themselves when trying to get direct access to a virtual machine e.g an EC2 instance. Key pairs work by having two private keys - a private key for VM and a matching private key for user.

A private key's file format means the file that my key is stored in. My private key's file format was .pem, which is widely accepted file format that most servers will be able to read/use. 

---

## Launching a public server

I had to change my EC2 instance's networking settings by changing the VPC and the subnet my EC2 instance was going to be launched in! I updated both to my  NextWork VPC and my Public Subnet respectively. I also used my existing Public security group.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because the NextWork public security group allows in all HTTP traffic - which would leave our private server much more vulnerable to securiy attacks/risks.

My private server's security group's source is my NextWork Public security group which means SSH traffic coming from the resources associated with that security group.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I used the 'VPC and more' option which gives me a  VPC resource map to use when creating the VPC and all of its components e.g security groups, route tables, internet gateways.

A VPC resource map is a visual diagram that maps out my VPC's components AND the relationships between them. A resource map is interactive i.e it will highlight the connections relevant to a resource that I highlight over. 

My new VPC has a CIDR block of 10.0.0.0/16. It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC(NextWork VPC) because VPCs already isolated from each other. Still, this is not best practice if we need VPC peering.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options either none or one each Availabity Zone for my VPC. This was because it is best practice (improves redundancy and high availablity) to have atleast subnet/AZ.

The set up page also offered to create NAT gateways, which are connectors/gateways that will let resources in my private subnet get access to the internet (e.g security updates) while still blocking off incoming traffic from the internet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-ec2_8ee57662)

---

---
