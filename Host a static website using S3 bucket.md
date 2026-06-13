<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use S3 to host a static website in AWS. I am doing this project to learn to learn about AWS and cloud services how they can be used to store objects in cloud and even host websites, eager to learn about it.

### Tools and concepts

Services I used were AWS S3. Key concepts I learnt include bucket policies, uploading static website files, index documentation, bucket endpoint URL and ACL(Access Control List) and how they control access to buckets.

### Time, challenges, and wins

This project took me approximately 2 hours including demo time and Quiz time. The most challenging part was resolving 403 forbidden error. It was most rewarding to see the website live to public.

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will open up S3 and then create storage space inside to start storing website files.

### How long it took to create the bucket

Creating an S3 bucket took me less than 6 minutes, needed to learn new things like block public access and ALCs but once that learned these things we can create buckets in shorter time in future.

### Region selection

The Region I picked for my S3 bucket was Mumbai, because the region is closest near my location. It is best to pick the region near my location because it lowers the time to retrive the things (aka latency) and cost. 

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no two AWS S3 buckets in the entire world can have same name.They have to be completely unique regardless of the region or the account ID

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will upload the website files in S3 bucket because no files = no website! Bucket is still empty let's get files inside bucket to need the website to host!

### Files I uploaded

I uploaded two files to my S3 bucket they were index.html (i.e this determines the structure i.e what goes inside the website) and folder and images and assets (i.e this will fill in the website with images and things will look)

### How the files work together

Both files are necessary for this project as index.html detmines the structure but the structure alone does not illustrate the content of website i.e index.html says "insert image here" it might not have the image, needs seperate image to supply

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will the make the website available to the world. This is called static website hosting and it is important because  the website will stay as "just files" while not doing static website host.

### Understanding website hosting

Website hosting means putting the website files on a web server, which is a special computer designed to turn the files into a website page that people can visit.

### How I enabled website hosting

To enable website hosting with my S3 bucket, I went to the properties tab and enabled static website hosting and also enabled the document as "index.html" as index document, i.e this is the document that we are trting to host.

### Access Control Lists (ACLs)

An ACL is a way to configure permission inside the buckets.Iam enabled ACLs so that I can access the website files later.There is a popup mentions that AWS recommends disable ACLs but keep it enable to learn how it work and compare with bucket policy

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which takes you (anyone on the internet) to the website that you are hosting!

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 forbidden error.The reason for this error was that objects in a bucket were default by public even though we switched off "Block all public access" the website files are still private.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will go inside the files that i have uploaded inside the bucket and make them public inside too because this will actually enable us to actually view content of the website. Once that is done, the website is officially live!

### How I resolved the 403 error

To resolve this 403 Forbidden error, updated the access settings of the files inside the bucket too. Using ACLs we made the bucket files public and we checked the S3 bucket endpoint and seen the webpage all loaded up!

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

### Understanding bucket policies

### What my bucket policy does

---

---
