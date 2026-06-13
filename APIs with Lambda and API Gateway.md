<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# APIs with Lambda + API Gateway

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-api)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-api_c9d0e1f2)

---

## Introducing Today's Project!

In this project, I will demonstrate how to set up an API using AWS Lambda and Amazon API Gateway. I am doing this project to learn how API's work and also setup a snazzy logic tier in my three-tier architecture! 

### Tools and concepts

Services I used were Amazon API gateway and AWS Lambda function. Key concepts I learnt include Lambda functions, API resources and methods, Lambda proxy integration, writing API documentation, API stages, invoke URLs for an API.

### Project reflection

This project took me approximately 2 hours including documentation. The most challenging part was understanding and writing the Lambda function. It was most rewarding to create the resource and methods - super informative! 

I chose to do this project to learn how to set up the logic tier of web app i.e the backend, or the brains of web application. This project definitely met the goals; and I learnt lot about how an API works along the way.

---

## Lambda functions

AWS Lambda is a service that lets to run code without having to manage any servers ourselves. That's why it is called a serverless service or Function as a Service (FaaS). I am using Lambda in this project to run code that helps us retrive data. 

The code I added to my function will grab a userID from a triggered event (i.e submitting a userID through a form/field in a website) and queries for a piece of data in DynamoDB that matches that userID. The code also takes of error handling.  

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-api_a1b2c3d5)

---

## API Gateway

APIs are tools that enable communication between systems. There are different types of APIs, like REST APIs or HTTP or WebSocket API. My API is a REST API, which means it uses HTTP methods and is compatible with most programming languages + Lambda.

Amazon API Gateway is an AWS service that helps developers with creating, maintaining and monitoring APIs  . I am using API Gateway in this project to connect my web app users with the Lambda function (i.e the serverless backend).

When a user makes a request i.e. click on a "Get User Data" button. API Gateway's role is to receive the traffic, determine whether or not it's authorized, and pass it through to Lambda if it is. API Gateway is also a traffic manage for requests.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-api_m3n4o5p6)

---

## API Resources and Methods

An API is made up of resources, which are different sections or different parts of the same API. For example, an API could have different sections for retriving user data vs retriving messaging data vs retriving product data in the same app. 

API methods define the actions you can perform on a resource. They are based on standard HTTP methods, which are different commands that let you interact with data over the internet. Each resource consists of methods, which are GET to retrieve, POST to add, PUT to update, and DELETE to remove data.

I created a GET method that will connect the API gateway with our Lambda function. This means that when an end user makes a request with the API e.g "api.com/users", the API knows to pass the event to our Lambda function if it is a GET request. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-api_c9d0e1f2)

---

## API Deployment

When I deploy an API, I deploy it to a specific stage. A stage is a snapshot of my API to manage different API versions. I deployed production stage aka 'prod', which is where there is live traffic and users that can access it. 

To visit my API, I visited the prod API's Invoke URL. The API displayed an error because the API is connected to a Lambda function that doesn't have permissions to DynamoDB (which might trigger authentication issue) + no DynamoDB table exists yet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-api_3ethryj2)

---

## API Documentation

---

---
