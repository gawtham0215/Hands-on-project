<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Creating a Private Subnet

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Creating a Private Subnet

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-private_afe1fdbd)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that allows users to provision a logically isolated section of the AWS cloud, creating a private network where they can launch AWS resources.

### How I used Amazon VPC in this project

I use Amazon VPC in today's project to create a private subnet by creating a route table, internet gateway and private network ACL.

### One thing I didn't expect in this project was...

The one thing you didn't expect in this project is none.

### This project took me...

The time I taken to complete this project is 1 hour including documentation.

---

## Private vs Public Subnets

The difference between public and private subnets is that public subnets are accesible and can access the internet and private subnets are completely isolated from the internet by default.

Having private subnets are useful because keeping resources is extremely important for the security of confidential resources/data.



My private and public subnets cannot have the same IPv4 CIDR block i.e the same range of addressess. The CIDR block for every subnet must be unique and cannot overlap with another subnet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-private_afe1fdbd)

---

## A dedicated route table

By default, my private subnet is associated with the default route table i.e a route table that has a route to an internet gateway.

I had to set up a new route table because my subnet cannot have a route an internet gateway.

My private subnet's dedicated route table only has one inbound and one outbound rule that allows internal communication i.e with a destination of another resource within my VPC.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-private_b4b904b5)

---

## A new network ACL

By default, my private subnet is associated with the default network ACL that's set up for every VPC created in my AWS account.

I set up a dedicated network ACL for my private subnet because a network ACL comes crucial in the event of security breaches where traffic that has compromised my public subnet can get access to my private subnet.

My new network ACL has two simple rules - simply deny all inbound traffic and simply deny all outbound traffic.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-private_1ed2cb07)

---

---
