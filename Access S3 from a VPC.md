<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Access S3 from a VPC

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-s3)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Access S3 from a VPC

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-s3_3e1e79a2)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon Virtual Private Cloud (VPC) is an AWS service that provides a logically isolated, private network within the AWS cloud, allowing users to define and control their own virtual network environment for launching AWS resources like EC2 instances.

### How I used Amazon VPC in this project

I am used Amazon VPC in today's project to create VPC and connecting EC2 instance with VPC that I am created. Then I am created access keys and S3 bucket, uploading objects in S3 bucket and creating empty file using EC2 and uploaded in S3 bucket.

### One thing I didn't expect in this project was...

The thing I didn't expect in this project is creating an empty file in EC2 instance and uploading in S3 bucket.

### This project took me...

The project took 2 hours including Demonstration, idenfying and troubleshooting the error.

---

## In the first part of my project...

### Step 1 - Architecture set up

In this step, Iwill launch a VPC with a public subnet and also launch an EC2 instance inside that public subnet.

### Step 2 - Connect to my EC2 instance

In this step, I directly access an EC2 instance using EC2 Instance Connect.

### Step 3 - Set up access keys

In this step, I create access keys so that my EC2 instance can have access to my AWS environment specifically, the ability to interact with an S3 bucket.

---

## Architecture set up

I started my project by launching a VPC with a public subnet and an EC2 instance inside that public subnet. 

I also set up an S3 buckets with two files inside.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-s3_4334d777)

---

## Running CLI commands

AWS CLI is a software I can download into a local computers terminal so that I can have access to my AWS account and different actions without needing to AWS management console. I have access to AWS CLI because  it is pre installed in EC2 instance.

The first command I ran was "aws s3 ls". This command is used to list all S3 buckets inside the AWS account (that the EC2 instance/application has access to). 

The second command I ran was 'aws configure'. This command is used to setup my EC2 instances's credentials in order to acces my AWS environment.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-s3_e7fa8776)

---

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured an access key ID, an access key, a default region name and a default region format.

Access keys are credentials that my EC2 instance + other applications/servers needs in order to get accessto my AWS environment i.e interact with my AWS resources/sevices. 

Secret access keys are like passwords for my access keys/credentials. My EC2 instance/other applications would need secret access keys as authentication and "log in" to my AWS environment.

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use IAM roles with permissions attached. This is a more secure way to grant access to an EC2 instance because it is much easier to track attach and detach IAM policies.

---

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I launch an Amazon S3 bucket with 2 files inside. This S3 bucket wil accessed by my EC2 instance to test the access to my AWS resources.

### Step 5 - Connecting to my S3 bucket

In this step, I am using AWS CLI commands to try control/manage our S3 bucket and interacting S3 bucket through my EC2 instance/VPC instead of AWS Management Console.

---

## Connecting to my S3 bucket

The first command I ran was "aws s3 ls". This command is used to list all S3 buckets inside the AWS account (that the EC2 instance/application has access to). 

When I ran the command "aws s3 ls" again, the terminal responded with "( Provided region_name 'asia pacific(Mumbai)' )" doesn't match a supported format. This indicated that I am not mentioned S3 bucket name.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-s3_4334d778)

---

## Connecting to my S3 bucket

Another CLI command I ran was aws s3 ls s3://nextwork-vpc-project-s3 which returned the objects inside the AWS S3 bucket.



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-s3_4334d779)

---

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command "sudo touch /tmp/test.txt" to create a blank .txt file in EC2 instance. This command creates an empty file in my EC2 instance.

The second command I ran was "aws s3 cp /tmp/test.txt s3://nextwork-vpc-project-s3" to upload that file into your bucket. This command will copy the file and its source file into the S3 bucket I have created.



The third command I ran was "aws s3 ls s3://nextwork-vpc-project-s3" which validated that S3 bucket and shows the object that I am previously uploaded and the empty text file using the command "sudo touch /tmp/test.txt".

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-s3_3e1e79a2)

---

---
