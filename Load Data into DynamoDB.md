<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Load Data into DynamoDB

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-dynamodb)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Load Data into a DynamoDB Table

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_b481c730)

---

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a non relational database service that provides fast, predictable performance and seamless scalability for applications. It is useful because it automatically handles infrastructure management, scaling, and maintenance.

### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create five tables! And used CloudShell and CLI to load data into tables quickly.I also compared DynamoDB to a relational databse by understanding how items and attributes work!

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is that I could perform a lot of actions using AWS CLI instead of AWS console e.g Creating tables, loading data and deleting table.

### This project took me...

This project took me approx 2 hours including documentation.

---

## Create a DynamoDB table

DynamoDB tables organises data using items and attributes! Every single item is recorded with a set of attributes. Items can have any number of attributes(minimum 1, for the partition key value ).

An attribute is a piece of data about an item in the DynamoDB table. For example if an item was a specific student, attributes could be StudentName, ProjectsComplete, Email, SignUpDate the number of attributes for each item is flexible!

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_a3cefee0)

---

## Read and Write Capacity

Read capacity units (RCUs) and write capacity units (WCUs) are units that measure my DynamoDB table's performance. DynamoDB pricing is based on RCUs and WCUs, so the more RCU/WCUs consumed, the more expensive the project.

Amazon DynamoDB's Free Tier covers 25 RCUs and WCUs monthly. I turned off auto scaling because it results in higher charges if DynamoDB automatically scales up my opreations(which charges or more WCUs and RCUs).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_ef47dd8f)

---

## Using CLI and CloudShell

AWS CloudShell is an environment that lets you to run code to interact with the AWS resources/services. Using AWS CloudShell is handy because AWS CLI is installed.

AWS CLI is a software that lets you to interact with resources using commands instead of clicks in the console. This is a very practical software that is preferred over AWS management console in day to day engineering operations in real world.

I ran a CLI command in AWS CloudShell called aws dynamodb create-table and I could even define the table name and its attributes all within the command.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_81e0258b)

---

## Loading Data with CLI

I ran a CLI command in AWS CloudShell that load multiple pieces of data(i.e, load multiple items) into the DynamoDB tables. I set up in the previous step. The AWS CLI command is structures as 'aws dynamodb batch-write-item -- request item file://x'.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_791c600b)

---

## Observing Item Attributes

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_b481c731)

I checked a ContentCatalog item, which had the following attributes Id, Authors, ContentType, Difficulty, Price, ProjectCategory, Published, Title and URL!

I checked another ContentCatalog item, which had a different set of attributes: Services, Title, VideoType etc.

---

## Benefits of DynamoDB

A benefit of DynamoDB over relational databases is flexibility, because the items have their own set of attributes. This great for scenarios where a table has diffrent types of data and some attributes that don't apply to all data in the table.

Another benefit over relational databases is speed, because DynamoDB can find items quickly using partition keys. This is faster than relational database which need to scan entire table to find specific piece of data.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-dynamodb_b481c730)

---

---
