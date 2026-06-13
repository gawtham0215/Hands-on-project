<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Three-Tier Web App

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-threetier)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Build a Three-Tier Web App

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_2b3c4d5e)

---

## Introducing Today's Project!

In this project, I will demonstrate how to setup a three tier web app from scratch! I will start with the presentation tier, then set up the logic tier and finally set up the data before trying them all together.

### Tools and concepts

Services I used were Amazon S3, CloudFront, DynamoDB, Lambda, API gateway. Key concepts I learnt include Lambda functions, CORS errors, updating the Javascript file with API invoke URL and testing the invoke URL within the browser.

### Project reflection

This project took me approximately 3 hours. The most challenging part was resolving the CORS errors in the API gateway and Lambda. It was most rewarding to see the final outcome - data getting returned in the web page.

I chose to do this project today to learn about the Three tier architecture and set up the web page. This project absolutely met my goals and I could see a fully functioning web app by the end.

---

## Presentation tier

For the presentation tier, I will set up how the website will be displayed and available to the end users. This is because the presentation tier is responsible for storing the website's files (Amazon S3) + website distribution (Amazon CloudFront).

I accessed my delivered website by visiting the CloudFront distribution's URL. This URL works because I also set up an origin access control that lets the S3 bucket access to only the CloudFront distribution. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_3a4b5c6d)

---

## Logic tier

For the logic tier, I will set up a lambda function to handle requests (e.g, look up userId to return some data) and also an API with API gateway to recieve requests from the user and hand over it to the Lambda. 

The Lambda function retrieves data by looking up a userId (that the user enters over the web app) in DynamoDB. The AWS SDK is used in the function code so that I can use templates and libraries that lets us find the correct DynamoDB + request data. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_6a7b8c9d)

---

## Data tier

For the data tier, I will set up a DynamoDB database that stores user data. At the moment, there is no user data for us to return to the web app's users. The data in the database will get returned once I set up the DynamoDB and connect it with Lambda. 

The partition key for the DynamoDB table is userId. This means that when the table looks up user data, it will look it up based on userId. Then it can return all data (values) related to the item with that ID.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_u1v2w3x4)

---

## Logic and Data tier

Once all three layers of the three-tier architecture are set up, the next step is to connect the presentation and logic tier. This is because currently there is no way for the API to catch requests that users make through the distributed site!

To test my API, I visited the invoke URL of the prod stage API. This let us test whether I can use the API and retrive user data. The results were some user data in JSON when I lookedup userId=1. This provided a logic + data tier connection. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_a112c3d5)

---

## Console Errors

The error in my distributed site was because there was an error within script.js (one of the website files I had uploaded into S3). The script.js file is referencing an prod stage API URL placeholder and not my API's actual URL. 

To resolve the error, I updated script.js by replacing the placholder text with the API's prod stage invoke URL. I then reuploaded it into S3 because the S3 bucket is still storing the last uploaded version (i.e. with an error).

I ran into a second error after updating script.js. This was an error with browser side CORS (Cross-Origin Resource Sharing) because API Gateway, by default, is only configured to allow requests from users directly running its invoke URL in the browser (not in the CloudFront).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_a1b2c3d5)

---

## Resolving CORS Errors

To resolve the CORS error, I first went into the API (in API Gateway) and enabled CORS on the /users resources. I then made sure GET requests are enabled and referenced the CloudFront domain as the domain getting access. 

I also updated the Lambda function code because it needs to be able to return CORS headers to show that it has the permission to invoke the API's URL and return a response. I added 'Access-Control-Allow-Origin' as a header in the response. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_1qthryj2)

---

## Fixed Solution

I verified the fixed connection between API Gateway and CloudFront by looking up user data in the distributed site again. In the final test, user data could be returned - so a user request in the presentation tier gets data from the data tier.  

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-threetier_2b3c4d5e)

---

---
