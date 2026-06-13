<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Fetch Data with AWS Lambda

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-lambda)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Fetch Data with AWS Lambda

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-lambda_p9thryj2)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use AWS Lambda to retrive data that's in a DynamoDB database. I am doing this project to learn how to set up the data tier of a web app and connect with a lambda function too (logic tier).

### Tools and concepts

Services I used were Amazon DynamoDB and AWS Lambda. Key concepts I learnt include Lambda functions, adding table items, testing Lambda functions, how to select the right permission policy, writing custom policies.

### Project reflection

This project took me approximately 1 hours 24 minutes. The most challenging part was writing the own inline policy. It was most rewarding to see the right data pop up when I run a function test.

I chose to do this project to learn about the data tier of a three-tier architecture. This project definitely met my goals as I learnt how to connect it to AWS lambda as well (logic tier) as well. 

---

## Project Setup

To set up my project, I created a database using DynamoDB. DynamoDB is a NoSQL database, so it is very fast at retrieval and flexible for data storage.  The partition key is userID, which means the key identified for each data is its userID.

In my DynamoDB table, I added a piece of data. DynamoDB is schemaless, which means that the data I add can come with new attributes, and every piece of data can have its set of attributes without affecting other data.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-lambda_a112c3d5)

### AWS Lambda

AWS Lambda is a service that lets us run code without having to manage servers. I am using Lambda in this project to create a function (i.e a piece of code) that retrives data from a DynamoDB table.

---

## AWS Lambda Function

My Lambda function has an execution role, which is set of permissions that it has to interact with other AWS services. By default, the role grants basic Lambda permissions, which are the permissions to write logs with CloudWatch e.g. error logs.

My Lambda function will retive the data from the DynamoDB database table. The first half of the code uses the AWS SDK for JavaScript to interact with DynamoDB. It takes a userId as input, grabs the corresponding data from the UserData table, and returns it to you. The second half of the code (i.e. beginning with try { ) handles potential errors during the database operation, so you get a tailored error message that tells you what went wrong.

The code uses AWS SDK, which is a set of tools that makes it easier for developers to use AWS in their application code. My code uses SDK to get access to DynamoDB actions i.e. read/retrive data items. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-lambda_a1b2c3d5)

---

## Function Testing

To test whether my Lambda function works, I wrote a function test in the Test tab in the Lambda console. The test is written in JSON. If the test is successful, I would see the correct piece of data in JSON when I query for userID=1.

The test displayed a 'success' because the function itself ran with no errors i.e. no syntax or dependency issues. But the function's response was actually an error because the Lambda function is retriving data from DynamoDB without permissions.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-lambda_u1v2w3x4)

---

## Function Permissions

To resolve the AccessDenied error, we are providing the Lambda function with the permission to perform *GetItem* on a DynamoDB table. This is because GetItem is the action that lambda is currently blocked from doing.

There were four DynamoDB permission policies I could choose from, but I didn't pick 'AWSLambdaDynamoDBExecutionRole, AWSLambdaInvocation-DynamoDB' because they relate to DynamoDB streams i.e. live updates of table items that have changed. 

I also didn't pick AmazonDynamoDBFullAccess because it would give the Lambda function the permission to do too many things with the table. AmazonDynamoDBReadOnlyAccess was the right choice because it secures the table from unauthorized access through Lambda function. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-lambda_3ethryj2)

---

## Final Testing and Reflection

To validate my new permission settings, I re-tested the Lambda function. The results were a piece of data and its three attributes (email, name, userID) because that is the exact data that we inputted in my database at the start of this project!

Web apps are a popular use case of using Lambda and DynamoDB. For example, I could use Lambda to retrive product information, user profiles, content (e.g. blogs or news articles) based on user queries or actions in the web app.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-lambda_p9thryj2)

---

## Enahancing Security

---

---
