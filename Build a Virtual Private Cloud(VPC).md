<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that allows users to create a logically isolated section within the AWS cloud, essentially a private network where they can launch AWS resources like EC2 instances.

I used Amazon VPC to create subntes and internet gateways to connect resources like AWS EC2 instance.

### Personal reflection

This project takes me around 1.5 hours including documentation.

The thing you didn't expect in this project is CIDR notation. 

---

## Virtual Private Clouds (VPCs)

### What I did in this step

### How VPCs work

Virtual Private Cloud (VPC) is a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. VPC allows to create IP address ranges, subnets, route tables, and gateways.

### Why there is a default VPC in AWS accounts

When you created your AWS account, AWS automatically sets up a default VPC for you to launch resources (e.g EC2 instances) and it is a handy starting point, especially for beginners, but you can always create custom VPCs to fit specific reqirements.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which means an range of addresses that my VPC can allocate to the resources deployed in my VPC.

---

## Subnets

### What I did in this step

### Creating and configuring subnets

Subnets are subsections of my VPC, just like how neighbourhoods are subsections of a city. There are subnets existing in my account, one for every Availablity Zone in the region I have setup. Since my region is Mumbai (ap-south-1), which has 3 AZ.

### Public vs private subnets

The difference between public and private subnets is a public subnet is connected to internet and a private subnet doesn't have direct internet access.I named my subnet in this is Subnet 1. For a subnet to be considered public is connect to gateway



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enable the auto-assign public IPv4 address for a subnet, any EC2 instance launched in that subnet will instantly get a public IP address.

---

## Internet gateways

### What I did in this step

### Setting up internet gateways

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.  An internet gateway connects city (VPC) and the outside world.

Attaching an internet gateway to a VPC means esources in your VPC can now access the internet. If I missed this step the connection established between the VPC and the internet gateway, my EC2 instance would still struggle to access the internet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

### Exploring CloudShell and CLI

### Debugging my setup

### Comparing CloudShell vs AWS Console

---

---
