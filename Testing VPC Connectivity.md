<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows users to create a logically isolated section within the AWS cloud and can launch resources. VPC provides control over network configuration, including IP address ranges, subnets, and route tables.

### How I used Amazon VPC in this project

I use Amazon VPC in today's project to create public server, testing connectivity between two EC2 instances and testing VPC connectivity between internet.

### One thing I didn't expect in this project was...

Thing I didn't expect in this project was testing the ping and curl commands giving different outputs.ping responds with a report on the performance of connectivity with my Private server, curl responded with HTML data from another public server.

### This project took me...

I took this project to complete in 2 hours including documentation.

---

## Connecting to an EC2 Instance

Connectivity means getting resources in our network to communicate with each other, and how well they can communicate/deliver data to each other. Without connectivity resources cannot communicate (e.g users cannot access the application).

My first connectivity test was whether I could connect to my network's Public server (an EC2 instance).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a tool provided by Amazon EC2 that allows us to directly access EC2 instance using AWS management console! we no longer need to manage key pairs or using SSH client to get access.

My first attempt at getting direct access to my public server resulted in an error, because my Private server had a security group that did not allow SSH traffic - it only allowed HTTP traffic i.e, a different protocol.

I fixed this error by adding a new inbound rule in my Private server's security group that allows SSH traffic from anywhere! 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a tool to test the connectivity between two servers and also the response. (i.e the performance of the connection). I used ping to test the connectivity between my Private server and Public server.

The ping command I ran was "ping 10.0.1.196" where 10.0.1.196 is the private IPv4 address of my Private Server  
(i.e my private instances IPv4 address).

The first ping returned NO replies from my private server. This meant security settings with my private server was blocking inbound(and or outbound) ICMP traffic, which is the traffic type of ping messages.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by enabling ICMP traffic in my private server's network ACLs and security groups! I also made sure the source I defined correctly pointed to my Public Subnet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a connectivity tool that tests connectivity from a server to another server AND retrives data from the target server too.

I used curl to test the connectivity between my network's  Public server with the public internet. This test is would be successful IF my internet gateway, network ACLs, security group and route tables were setup correctly.

### Ping vs Curl

Ping and curl are different because they return different responses to my Public server's Terminal - ping responds with a report on the performance of connectivity with my Private server, curl responded with HTML data from another public server!

---

## Connectivity to the Internet

I ran the curl command ("curl https://learn.nextwork.org/projects/aws-host-a-website-on-s3") which returned the HTML content of NextWork's first project guide.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-connectivity_8ee57662)

---

---
