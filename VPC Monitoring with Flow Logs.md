<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Monitoring with Flow Logs

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-monitoring)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## VPC Monitoring with Flow Logs

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_3e1e79a1)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows users to create a logically isolated section within the AWS cloud,  can launch AWS resources like EC2 instances. It provides a way to control network configurations, including IP address ranges, subnets.

### How I used Amazon VPC in this project

In today's project  I achieved two big milestones! First I learnt to trobleshoot the VPC peering connectivity issues. Secondly I learnt how to monitor network traffic using VPC flow logs.

### One thing I didn't expect in this project was...

I didn't expect in this project is logs insights has lots of built in queries that give us many options on how I would analyze the network traffic.

### This project took me...

I took 2 hours to complete the project by trouble the VPC peering connction and monitoring traffic flow using VPC flow logs, including documentation.

---

## In the first part of my project...

### Step 1 - Set up VPCs

In this project, I will setup a VPC, EC2 instances in the public and private subnets. Set up two VPCs and test their peering connection. Set up VPC Flow Logs that collect network traffic data. Analyse network traffic using CloudWatch's Log Insights.

### Step 2 - Launch EC2 instances

In this step, I launched two EC2 instances - one in each VPC. Doing this is important to setup the remainder of this project and EC2 instance will generate the traffic that VPC flow logs will monitor. 

### Step 3 - Set up Logs

In this step, I am setting up VPC flow flows to start monitoring network traffic and also setting up a storage space for my flow logs.

### Step 4 - Set IAM permissions for Logs

In this step, I provide VPC flow logs with the permission to create logs and upload them into our log group in Cloudwatch.  

---

## Multi-VPC Architecture

I started my project by launching two VPCs! I created two subnets(i.e one public subnet for each VPC) with no private subnets.

The CIDR blocks for VPCs 1 and 2 are 10.1.0.0/16 and 10.2.0.0/16 respectively.They have to be unique because having overlapping CIDR blocks will cause network routing/traffic issues down the line when traffic is needing to go from one VPC to another.

### I also launched EC2 instances in each subnet

My EC2 instances security groups allow SSH and IPMC type traffic protocol. This is because EC2 instance connect will need to access my EC2 instance using SSH type traffic and because I need to allow ICMP type traffic for connectivity test. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_e7fa8775)

---

## Logs

Logs are like a diary for your computer systems - they are detailed records of any kind of activity related to traffic/resource/AWS service that the log is tracking. 

Log groups are grouping of logs i.e logs that belong to the project/application/source are often in a log group together!

### I also set up a flow log for VPC 1

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_e8398869)

---

## IAM Policy and Roles

I created an IAM policy so that I can define a rule that allows policy holders e.g my VPC Flow Logs service that ability to create log streams and upload them in CloudWatch.

I also created an IAM role because services like VPC flows has associated with a role instead with JSON! Creating an IAM role will be necessary to give VPC flow logs the access it needs to record and upload logs.

A custom trust policy is a specific type of policy used for designing who/what is allowed access to the IAM role.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_4334d777)

---

## In the second part of my project...

### Step 5 - Ping testing and troubleshooting

In this step, I am generating network traffic! This becomes Important when communicating about cloudworks/cloud networking/ or cloud engineering.

### Step 6 - Set up a peering connection

In this step, I am setting up a peering connection that so that VPCs 1 and 2 can talk directly to each other.

### Step 7 - Analyze flow logs

In this step, I am tracking the network data that's collected on VPCs and analyse the data to extract insights.  

---

## Connectivity troubleshooting

My first ping test between my EC2 instances had no replies, which means ICMP traffic could be blocked by security group/network ACLs or maybe our traffic is being routed to wrong path.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_99d4ba42)

I could receive ping replies if I ran the ping test using the other instance's public IP address, which means the second EC2 instance is actually allowing ICMP traffic.

---

## Connectivity troubleshooting

Start your response with 'Looking at VPC 1's route table, I identified that the ping test with Instance 2's private address failed because I do not have a route in my VPC's route table that directs traffic from one VPC to another VPC.

### To solve this, I set up a peering connection between my VPCs

I also updated both VPCs' route tables so that traffic from one of the VPCs heading to the other VPC can get directed through the peeing conncetion.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_7316a13d)

---

## Connectivity troubleshooting

I received ping replies from Instance 2's private IP address! This means setting up the peering connection and the route table solved the connectivity error of VPC's traffic not being able to navigate from one VPC to another VPC.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_4ec7821f)

---

## Analyzing flow logs

Flow logs tell us about the source and destination of the network traffic, the amount of data transferred, whether the traffic is accepted or rejected.

For example, the flow log I've captured tells us the traffic went from 89.248.163.188 to 10.1.11.46 and I can also extract that the traffic was accepted by security groups and network ACLs of my VPC.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_d116818e)

---

## Logs Insights

Logs Insights is a feature of CloudWatch Logs that allows users to search, analyze, and visualize log data stored in CloudWatch. It provides a way to query logs using a SQL-like language, enabling users to quickly identify trends, troubleshoot issue.

I ran the query top 10 byte transfers by source and destination IP addresses. This query analyzes the flow logs collected on EC2 instance 1 and return top 10 IP addresses based on the amount of data transferred betwwen them!

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-monitoring_3e1e79a1)

---

---
