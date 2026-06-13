<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use Terraform to launch an S3 bucket. The goal is to install terraform troubleshoot any errors (i.e installing the CLI) and then successfully plan and apply the terraform configuration to launch a S3 bucket.

### Tools and concepts

Services I used were Terraform, AWS S3, AWS CLI and AWS IAM. Key concepts I learnt include infrastructure as code, configuration of files, modularity of code using providers, plugins, state files, lock files(Terraform concepts).

### Project reflection

This project took me approximately 1 hours and 40 minutes including secret mission. The most challenging part was customizing S3 configuration using the official terraform documentation. It was most rewarding to see a local image uploaded into S3 bucket.

I chose to do this project today because to learn about the Infrastructure as Code (IaC) using terraform and learned about Terraform and wanted to make a start. This project met my goals because i could actually install and setup the Terraform and used it launch the resources in the AWS environment. Something that would make learning with NextWork even better.

---

## Introducing Terraform

Terraform is a tool for managing the IT resources using code. You use Terraform to process a configuration file you have prepared the details of desired state of the infrastructure Terraform then creates/updates/deletes to setup that desired state.

Terraform is one of the most popular tools used for infrastructure as code (IaC), which is a way to manage the infrastructure instead of manually managing resources using the console/text commands in CLI, IaC automates the process with the code.

Terraform uses configuration files to understand the desired state of our infrastructure "main.tf" is the main configuration file that I am use in Terraform to describe that desired state.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

The configuration is structured in self-contained “blocks" and might notice this in the main.tf file - the code is split into three blocks

The advantage of doing this is because
A resource block describes what to create, such as a storage bucket or virtual machine, and how it should look.

By keeping each piece of your infrastructure in its own block, the file stays easy to read and you can tweak one part without touching the rest of your setup!

### My main.tf configuration has three blocks

Three blocks in my main.tf file structured in the following way
The first block indicates... 
Provider "aws"
This tells Terraform to use AWS. A "provider" is a plugin that lets Terraform work with a specific cloud service. The provider turns your configuration into API calls that create and manage your infrastructure.

The second block provisions..
Resource "aws_s3_bucket" "my_bucket"
This creates an S3 bucket. my_bucket is an internal name that other blocks of code in main.tf will use to reference your bucket.

The third block manages...
Resource "aws_s3_bucket_public_access_block" "my_bucket_public_access_block"
This controls who can access your S3 bucket. All the settings like block_public_acls, ignore_public_acls, block_public_policy, and restrict_public_buckets are set to true to prevent public access to your bucket and its contents.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

---

## Terraform commands

I ran 'terraform init' to initialize Terraform. This means getting up to setup the backend to store state files, and install the necessary plugins i.e AWS provider plugin. 

Next, I ran 'terraform plan' to get terraform to compare infrastructure/resources in the "main.tf" and compare that against the infrastructure's current state. Then share back the execution plan i.e how running main.tf will impact the infrastructure e.g create resources.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

When I tried to plan my Terraform configuration, I received an error message that says 'no valid credentials found'  because my local terminal was not setup with AWS setup credentials yet. This needs to be setup to use the AWS provider plugin.

To resolve my error, first I installed AWS CLI, which is AWS command line tool for interacting with the AWS environment instead of using the AWS management console, the CLI lets to run commands to do the same things from my local computer.

I set up AWS access keys so that I have a way to 'log in' to my AWS account over the CLI in my local terminal. Once the access keys and secret access keys are passed through 'AWS configure' my terminal now has the necessary AWS credentials.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_7j8k9l0m)

---

## Lanching the S3 Bucket

I ran 'terraform apply' to get terrform to apply the changes /updates it showed us when i run run terraform apply. Running 'terraform apply' will affect my AWS account by creating two resources - an s3 bucket and its set of permissions in AWS user account.

The sequence of running terraform init, plan, and apply is crucial because I need to initialize terraform first before I get to (1) make any comparisions between main.tf and current infrastructure or (2) connect AWS in the first place.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

I created a new resource block to upload an image to the S3 bucket using terraform.

We need to run terraform apply again because I have updated my Terraform file which means there are some changes need to review and compare with current infrastructure. This time one new resource is created(image).

To validate that I have updated my configuration successfully, I checked the S3 bucket and confirmed that a new image is inside the bucket. I also downloaded the image back to us and confirmed that it was the correct image that was initially uploaded.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-terraform1_9o0p1a2s)

---

---
