<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Query Data with DynamoDB

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-query)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Query Data with DynamoDB

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-query_733d9399)

---

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a non relational database service. DynamoDB organize data into tables, where data is organised using items and attributes. 

### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create and load tables, ran queries over the AWS CLI and the console. We also procesed transactions(ran multiple operations as one) to manage related data.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is that DynamoDB queries have to use the partition key. In scenarios where we want to find data using only other attributes, I run into an error!

### This project took me...

This project took me 1 hour 40 minutes including documentation.

---

## Querying DynamoDB Tables

A partition key is the main tag/ID that DynamoDB will use to partition its tables items. Every item must have a partition key, the partition key's value must be unique unless a table has a sort key!

A sort key is a second filter/tag that DynamoDB can use to search for specific items. If a table has a sort key, then each item's primary key is made of its partition key + sort key i.e partition key values can be same if sort keys are not!  

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-query_d105b0b0)

---

## Limits of Using DynamoDB

I ran into an error when I queried for all comments made by a specific user.  This was because queries MUST use the table's partition key and the PostedBy attribute (which I used to filter the result) was not.

Insights we could extract from our Comment table includes all comments left on a single post and even sorted/filtered by comment date/time. Insights we can't easily extract from the Comment table includes all comments made by a specfic user.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-query_cb3e260c)

---

## Running Queries with CLI

A query I ran in CloudShell was aws-dynamodb-get-item.
This query will grab the item from the table and with the partition key value that I described in the command.

Query options I could add to my query are consistent-read (which provides strongly consistent read), projection-expression(only return certain attributes), return-consumed-capacity(which returns the number of capacity consumed).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-query_733d9399)

---

## Transactions

A transaction is a group of operations that are bundled together and get executed as one. For the transaction to succeed, all operations within that transaction must process successfully.

I ran a transaction using AWS CLI commands that run on AWS CloudShell. This transaction did two things first it added a new item to a table (Comment), then the transaction updated an item in the Forum table(Event's Comment count increased by 1).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-query_2f65f83e)

---

---
