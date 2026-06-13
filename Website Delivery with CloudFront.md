<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Website Delivery with CloudFront

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-cloudfront)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Website Delivery with CloudFront

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-cloudfront_1dddddwe)

---

## Introducing Today's Project!

In this project, I will demonstrate  how to use CloudFront to deliver a website globally. I am doing this project to learn about CDNs (Content Delivery Networks) and to setup the presentation of a Three-tier architecture.

### Tools and concepts

Services I used were Amazon S3 and CloudFront Key concepts I learnt include content delivery network (CDN),  distributions, origin access control (OAC), perfomance load times, S3 static web hosting vs Cloudfront. 

### Project reflection

This project took me approximately 2 hours including troubleshooting the CloudFront distribution. The most challenging part was resolving the error of CloudFront distribution. It was most rewarding to see the output.

I chose to do this project today because to learn about cloudfront distribution. This project met the goals and i have successfully built the presentation of a three-tier architecture. 

---

## Set Up S3 and Website Files

I started the project by creating an S3 bucket to store the website files. I can't use CloudFront for this task because CloudFront is not a storage service - it is a content delivery service for objects that are already somewhere.

The three files that make up my website are index.html, which outlines the text and images (i.e. the structure) of my websites ; style.css, which adds styling to HTML elements and script.js, which interactive elements like form submissions.

I validated that my website files work by opening index.html locally on our website. I saw a simply webpage without any errors, so the three files can be uploaded into S3 buckets.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-cloudfront_qgo7wcd3)

---

## Exploring Amazon CloudFront

Amazon CloudFront is a Content Delivery Network (CDN), which means it caches web content (i.e websites files) to edge locations/servers around the world. Businesses and developers use CloudFront because it speeds up their website's performance. 

To use Amazon CloudFront, I am settting up distributions, which are instructions that I tell CloudFront how to deliver the content. I set up a distribution for the website and the origin is the S3 bucket. 

My CloudFront distribution's default root object is index.html  This means the users may visit my website's root URL, they will see the content described in index.html 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-cloudfront_qgo7wcdt)

---

## Handling Access Issues

When I tried visiting my distributed website, I ran into an access denied error because I haven't setup S3 bucket policy permission to access it and need IAM policy to access it.

My distribution's origin access settings were not changed. This caused the access denied error because CloudFront did not have access to S3 bucket.

To resolve the error, I set up origin access control (OAC). An origin access control (OAC) is a special user for CloudFront that prevents unwanted access for the S3 bucket. An OAC lets you keep your S3 bucket and objects not publicly accessible, while still making sure they can be accessed through CloudFront. OAC also gives you granular control over how CloudFront accesses the content. For example, you can add other authentication or security settings to make sure only legitimate users can access your content.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-cloudfront_egrhntyu)

---

## Updating S3 Permissions

Once I set up my OAC, I still needed to update my bucket policy because its objects are private to anyone including CloudFront. Just creating the OAC does not mean that CloudFront automatically has access to S3.

Creating an OAC automatically gives me a policy I could copy, which grants the access for users to access S3 buckets for everyone including CloudFront.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-networks-cloudfront_eg98ntyu)

---

## S3 vs CloudFront for Hosting

---

## S3 vs CloudFront Load Times

---

---
