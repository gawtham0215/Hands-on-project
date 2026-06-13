<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Endpoints

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-endpoints)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## VPC Endpoints

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_09bcaa8a)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon Virtual Private Cloud (VPC) is an AWS service that lets you launch AWS resources into a virtual network that you define, giving you control over your network's configuration, security, and how it interacts with the internet.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create Endpoint and also Endpoint policy for accessing the Amazon S3 bucket rather than other ways to access Amazon S3 bucket.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was by creating a VPC Endpoint policy for S3 bucket and got error and resolved the error by modifying the Endpoint route table to access only through Endpoint by blocking other ways to access S3.

### This project took me...

This project took me 2 hours including documentation by creating the super security for S3 bucket by creating the policy for VPC endpoint to access S3.

---

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will Set up the foundations for VPC endpoint architecture by launching a VPC, an EC2 instance and a S3 bucket.

### Step 2 - Connect to EC2 instance

In this step, I am connecting directly to EC2 Instance using EC2 Instance Connect. Connecting to EC2 instance will help to access the S3 bucket and running commands later in this project.

### Step 3 - Set up access keys

In this step, I will create access keys for S3 bucket so that my EC2 instance can have access to my AWS environment and it has  the ability to interact with an S3 bucket.


### Step 4 - Interact with S3 bucket

In this step, I will launch an Amazon S3 bucket with 2 files inside. This S3 bucket wil accessed by my EC2 instance to test the access to my AWS resources.


---

## Architecture set up

I started my project by creating a VPC, an EC2 instance and launching those resource for VPC endpoint archtecture.

I also set up the S3 bucket by uploading two files into the new bucket.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_4334d777)

---

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured my AWS Secrect key, Secrect key ID, my AWS region name and my AWS region output format. 

Access keys are credentials that an EC2 instance/other server/application would need in order to get access to the AWS environment e.g creating resources, reading what's inside my AWS account.  

Secret access keys are like passwords for my access keys/credentials. My EC2 instance/other applications would need secret access keys as authentication and "log in" to my AWS environment.

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use IAM roles with permissions attached. This is a more secure way to grant access to an EC2 instance because it is much easier to track attach and detach IAM policies.

---

## Connecting to my S3 bucket

The command I ran was "aws s3 ls". This command is used to list all the buckets in AWS account.

The terminal responded with AWS environment and displays the S3 buckets. This indicated that the access keys I set up was interact with EC2 instance and VPC and displays the buckets

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_4334d778)

---

## Connecting to my S3 bucket

Another CLI command I ran was "aws s3 ls s3://nextwork-vpc-project-s3" which returned the objects inside the AWS S3 bucket.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_4334d779)

---

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command "sudo touch /tmp/test.txt" to create a blank .txt file in EC2 instance. This command creates an empty file in my EC2 instance.

The second command I ran was "aws s3 cp /tmp/test.txt s3://nextwork-vpc-project-s3" to upload that file into your bucket. This command will copy the file and its source file into the S3 bucket I have created.

The third command I ran was "aws s3 ls s3://nextwork-vpc-project-s3" which validated that S3 bucket and shows the object that I am previously uploaded and the empty text file using the command "sudo touch /tmp/test.txt".

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_3e1e79a2)

---

## In the second part of my project...

### Step 5 - Set up a Gateway

In this step, I am setting up the VPC endpoint so that communication between my VPC and other services (espcially S3) is direct and secure.

### Step 6 - Bucket policies

In this step, I will test my endpoint connection by blocking off all traffic to my S3 bucket, except for traffic coming from my endpoint.

### Step 7 - Update route tables

In this step, I will test my VPC endpoint connection between my S3 bucket and EC2 instance 

### Step 8 - Validate endpoint conection

In this step, I am going validate my VPC endpoint set up one more time. Iam also going to use endpoint policies to restict my EC2 instance's access to the AWS environment.

---

## Setting up a Gateway

I set up an S3 Gateway, which is a type of endpoint specifically designed for AWS S3. Gateways work by updating the route table of associated subnets, so that S3 bound traffic goes through the Gateway instead of the internet.

### What are endpoints?

An endpoint is a VPC component that allows my VPC to have direct connection with AWS services, so that traffic does not have to go through public internet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_09bcaa8a)

---

## Bucket policies

A bucket policy is a type of policy that has granular control over who has access to an S3 bucket, and what are the actions that they can perform.

My bucket policy will deny traffic all sources - except  for traffic coming from my VPC endpoint.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_7316a13d)

---

## Bucket policies

Right after saving my bucket policy, my S3 bucket page showed 'denied access' warnings. This was because my policy denies all actions unless they come from your VPC endpoint.

I also had to update my route table because my route table by default didn't provide a route for traffic in my public subnet to the VPC endpoint.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_4ec7821f)

---

## Route table updates

To update my route table, I visited the Endpoints page of my VPC console and I modified the route table from there to associate my VPC's public subnet.

After updating my public subnet's route table, my EC2 instance could connect with my S3 bucket! Access was no longer denied!

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_d116818e)

---

## Endpoint policies

An endpoint policy is a type of policy designed for specifying the range of resources and actions permitted by a endpoint.

I updated my endpoint's policy by changing the effect from "Allow" to "Deny" ! I could see the effect of this right away, because my EC2 instance was again denied access to S3 bucket when I tried to run another AWS S3 command

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-endpoints_3e1e79a3)

---

---
