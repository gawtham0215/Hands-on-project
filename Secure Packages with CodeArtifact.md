<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Secure Packages with CodeArtifact

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codeartifact-updated)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codeartifact-updated_1d79e699)

---

## Introducing Today's Project!

In this project, I will demonstrate how to setup CodeArtifact as my CI/CD pipeline's artifact repository. I am doing this project to learn the importance and value of artifact repository. It is a huge time saver :)

### Key tools and concepts

Services I used were CodeArtifacts, IAM, EC2, Github and VS code terminal. Key concepts I learnt include artifact repositories, connecting maven with CodeArtifact and setting up IAM permission to EC2 instance to acess CodeArtifact.

### Project reflection

This project took me approximately 2 hours. The most challenging part was troubleshoot the domain key access to EC2 instance. It was most rewarding to see CodeArtifact was filled up with heaps of packages when the connection was all setup.



This project is part three of a series of DevOps projects where I am building a CI/CD pipeline! I will be working on the next project in the coming day.

---

## CodeArtifact Repository

CodeArtifact is artifact repository service, which means I can use it to create repositories to store the web app's packages and dependencies. Engineering teams use artifact repositories for security, control and reliablity.

A domain is like a folder that holds together multiple repositories under the same project or same organization. They are helpful for setting up permission settings for multiple CodeArtifact repositories in one go. My domain is called nextwork.

A CodeArtifact repository can have an upstream repository, which means a public source of packages that Maven can visit if they can't find it in my local CodeArtifact repository. My repository's upstream repository is "maven-central-store" repository

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codeartifact-updated_n4o5p6q7)

---

## CodeArtifact Security

### Issue

To access CodeArtifact, I need an authentication token that allows the EC2 instance to access CodeArtifact repositories.
I ran into an error when retrieving a token because my EC2 instance is not have the permission to access the AWS resources.

### Resolution

To resolve the error with my security token, I am created the IAM policy that grant access to CodeArtifact and attached IAM role to EC2 instance and I resolved the error by access to request the authorization token for Repository in EC2 instance.

Advantages of using IAM roles instead of handcoded credentials is that IAM roles are secure and scalable! on the other hand handcoded credentials are more vulnerable in security attacks and misused (resulting in errors, loss and delays).

---

## The JSON policy attached to my role

The JSON policy I set up grants access to CodeArtifact specifically, it grants access to three key actions related to CodeArtifacts - retriving the token authentication, finding the repository (endpoint)and viewing the packages inside the repository.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codeartifact-updated_23rp7q8r9)

---

## Maven and CodeArtifact

### To test the connection between Maven and CodeArtifact, I compiled my web app using settings.xml

The settings.xml file configures Maven to use the CodeArtifact repository. It supplies the the name and the authentication token to get access to the CodeArtifact repository and also tell the Maven to use which one when i have multiple repositories.

Compiling means the process of transisting the web app code source code into something that machines can run. Maven is the compiler that i am used, so i asked it to compile the web app's code. While compiling maven will put all package together. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codeartifact-updated_c17eace8)

---

## Verify Connection

After compiling, I checked the CodeArtifact repository and I noticed four pages of packages inside! This tells that I have successfully stored the web app's dependencies in an artifact repository.  



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codeartifact-updated_1d79e699)

---

## Uploading My Own Packages

---

---
