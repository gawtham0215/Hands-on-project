<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Peering

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-peering)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## VPC Peering

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_88727bef)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows users to create a logically isolated section within the AWS cloud and launch AWS resources like EC2 instances, provides a way to control network configurations, including IP address ranges, subnets, route tables.

### How I used Amazon VPC in this project

I use Amazon VPC in today's project to set a multi VPC architecture, create a peering connection between them and update security group rules to run a successful connectivity test to validate VPC peering setup. 

### One thing I didn't expect in this project was...

I didn't expect to need a public IPv4 address for EC2 Instance Connect to work. Also didn't expect that Elastic IPs can assign static IPv4 addresses to resources.

### This project took me...

I take two hours to complete this project including documentation.

---

## In the first part of my project...

### Step 1 - Set up my VPC

In this step we are using the VPC resource map/launch wizard to create two VPCs and their components in just minutes. 

### Step 2 - Create a Peering Connection

I am setting up a VPC peering connection, which is a VPC component designed to directly connect two VPCs together.

### Step 3 - Update Route Tables

In this step, I am editing the route table for VPC 1 and VPC 2 so that traffic can be directed to the peering connection setup

### Step 4 - Launch EC2 Instances

In this step I am launching an EC2 instances in each of the VPCs (VPC 1 and VPC 2), so that we can directly connect with our instances later and test our VPC peering connection.

---

## Multi-VPC Architecture

I started my project by launching two VPCs and has unique CIDR blocks and they have one public subnet.

The CIDR blocks for VPCs 1 and 2 are 10.1.0.0/16 and 10.2.0.0/16 respectively. They have to be unique because once set up a VPC peering connection (between two VPCs), route tables need unique address for correct routing accross VPCs.

### I also launched 2 EC2 instances

I didn't set up key pairs for these EC2 instances as I am using EC2 Instance Connect to directly connect with my EC2 instances which handles key pair creation and management.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_11111111)

---

## VPC Peering

A VPC peering connection is known as VPC Network Peering allows two VPC networks to connect and communicate using internal IP address and enables instances in different VPCs to interact as if they were in the same network and enhance connectivity.

VPCs would use peering connections to facilitate direct, private network connections between separate networks, allowing resources in those networks to communicate with each and enable efficient data transfer and resource sharing.

The difference between a Requester and an Accepter in a peering connection is the Requester is the VPC that initiates the peering connection request, while the Acceptor is the VPC that receives and accepts the request to establish the connection.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_1cbb1b88)

---

## Updating route tables

After accepting a peering connection on my VPCs' route tables need to be updated because traffic between VPCs still need directions from the each VPC's route table in order to get to their other VPC.

My VPCs' new routes have a destination of other VPC's CIDR block. The routes' target was the peering connection that I setup. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_4a9e8014)

---

## In the second part of my project...

### Step 5 - Use EC2 Instance Connect

In this step I will use EC2 Instance Connect to connect to my EC2 instances try talk to the other to test the VPC peering connection.

### Step 6 - Connect to EC2 Instance 1

In this step I am reattempting connection to Instance - NextWork VPC 1, and resolving another preventing us from using EC2 instance Connect to directly connect with the instance.

### Step 7 - Test VPC Peering

In this step, I am going to use Instance - NextWork VPC 1 to attempt a direct Instance - NextWork VPC 2 so that I can validate that my peering connection is setup properly.

---

## Troubleshooting Instance Connect

Next, I used EC2 Instance Connect to directly connect with Instance - NextWork VPC 1 just by using AWS management console. 

I was stopped from using EC2 Instance Connect as my EC2 did not have a IPv4 public address. In order for EC2 Instance Connect to work, the EC2 instance must have a public IPv4 address and in a public subnet. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_7685490c)

---

## Elastic IP addresses

To resolve this error, I set up Elastic IP addresses. Elastic IP addresses are static public IPv4 addresses that we can request for our AWS account and delegate to specific resources.

Associating an Elastic IP address resolved the error because it gives my EC2 instances a public address, fulfilling the requirements for EC2 Instance Connect to work

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_45663498)

---

## Troubleshooting ping issues

To test VPC peering, I ran the command 10.2.xxx.xxx i.e the private IPv4 address of the other EC2 instance in VPC 2

A successful ping test would validate my VPC peering connection - this ping test wouldn't get any replies from other EC2 instance if the peering connection didn't successfully connect my two VPCs.

I had to update my second EC2 instance's security group because it was not letting in ICMP traffic - which is a traffic type of ping message. I added a new rule that allows ICMP traffic coming in from any resource in VPC 2.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-peering_7a29d352)

---

---
