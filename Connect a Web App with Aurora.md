<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a Web App with Aurora

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-webapp)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Connect a Web App to Amazon Aurora

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-webapp_1709b26b)

---

## Introducing Today's Project!

### What is Amazon Aurora?

Amazon Aurora is a fully managed relational database service from AWS that is compatible with MySQL and PostgreSQL and useful because it can hold large databases effectively.

### How I used Amazon Aurora in this project

In today's project, I used Amazon Aurora to connect with a web app where I could add data on a web app.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how tangible the databases are in being able to see data you have entered.

### This project took me...

I did this project and it took approximately 2 Hours including documentation.

---

## Creating a Web App

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-webapp_b7999168)

To connect to my EC2 instance, I used windows powershell to connect ssh [ssh -i NextWorkAuroraApp.pem ec2-user@ec2-13-233-107-54.ap-south-1.compute.amazonaws.com] it asks the permission and it connect to EC2 instance.

To help me create my web app, I first made sure that all my software on EC2 instance was updated and that I installed all the tools that I need on EC2 instance to start the web app (Apache, PHP, PHP library, MariaDB).

---

## Connecting my Web App to Aurora

I set up my EC2 instance's connection details to my database using Windows Powershell and by writing into the dbinfo.inc file using nano command.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-webapp_1709b25b)

---

## My Web App Upgrade

Next, I upgraded my web app by adding a SamplePage (a PHP file) that has a header and looks like a form that I can add data into that PHP file.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-webapp_2709b25b)

---

## Testing my Web App

To make sure my web app was working correctly, I used MySQL CLI to ensure that, I was able to retrive all the data  I had entered through the webapp.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-databases-webapp_1409z22b)

---

---
