<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows to create a logically isolated section within the AWS cloud, for your AWS resources.It gives you control over your virtual networking environment, including IP address, subnets, route tables, and security groups.

### How I used Amazon VPC in this project

I use Amazon VPC in today's project to create subnet, route table, internet gateway, and Network ACL(Access Control List).

### One thing I didn't expect in this project was...

The  one thing you didn't expect in this project is rules of route tables.

### This project took me...

This projects takes 1 hour to complete including documentation.

---

## Route tables

Route table are like the GPS that directs traffic within my VPC to the correct destination. 

Routes tables are needed to make a subnet public because subnets needs to have a route to an internet gateway in order to be considered public. A route table is the only way to establish this connection.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target, which mean the destination is the range of IP addresses that traffic in my VPC is trying to reach, the target is the road or path that the traffic will have to take to get to its destination.

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of my NextWork IG (internet gateway).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are like security guards that monitor both inbound and outbound traffic at the resource level i.e every single resources in a subnet/VPC has a security group. 

### Inbound vs Outbound rules

Inbound rules are rules that monitor/restrict inbound traffic (e.g users visiting a web app). I configured an inbound rule that allows all all HTTP traffic.

Inbound rules are rules that monitor/restrict outbound traffic (e.g a web app requesting the data from a public source).  By default, my security group's outbound rule will allow all outbound traffic.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are like traffic cops stationed at every entry and exit point of your subnet, checking each data packet against a table of ACL rules before allowing them through.

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that security group secures my network at the resource level while network ACLs secures my network at the subnet level.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will setup to allow all incoming traffic and outgoing traffic. 

In contrast, a custom ACL’s inbound rules are automatically set to deny to all incoming traffic and outbound rules are automatically set to deny to all outgoing traffic.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

---

---
