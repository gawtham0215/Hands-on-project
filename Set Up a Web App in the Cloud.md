<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, I will set up the foundation of CI/CD pipelearn from creating a web app from scratch by launching an EC2 instance and connect it to the instance using VS code to generate web app inside. I'm doing this project to learn about CI/CD 

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in coming days :)

I did this project to kick start the 7 day DevOps project. Challenge well accepted now! And it's great to set up a web app in the cloud using EC2 instance and VScode terminal.

### Key tools and concepts

Services I used in this project is VScode and AWS EC2. Key concepts I learnt include SSH connection and using an IDE launching an instance, editing index.jsp file using EC2 instance keypair.

### Project reflection

This project took me approximately was 2 hours 30 minutes including documentation. The challenging part was connecting VS Code with EC2 Instance and faced connection error and trobleshoot the error by configuring the identityfile in .ssh folder.

One thing I didn't expect in this project is by editing the web application folder by using the IDE terminal instead of using EC2 instance connect and understood the difference between them.

---

## Launching an EC2 instance

### What I did in this step

In this step, Iam launching an EC2 instance in AWS account and going to setup the network settings which helps up sure that I can find my EC2 instance and keypair, which helps to make sure that i had permission to use the EC2 instance while I access.

I started this project by launching an EC2 instance because that EC2 instances are computers that live in the cloud, I want the web app to live entirely in the cloud and launching the EC2 instance even to develop the web app code.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_7852fbf3)

### I also enabled SSH

SSH is a protocol used to make sure only authorized users can access a remote server like EC2 instances. I enabled SSH so that I can securly connect to EC2 instance and made sure that it allows SSH traffic from my IP address for security purpose.

### Key pairs

A key pair in EC2 is like the keys to your virtual computer. A key pair lets you securely access your EC2 instance.While using the private key, it verifies that you're the one allowed to access that specific virtual machine, keeping everything secure

### Downloaded key pair file

Once I set up my key pair, AWS automatically downloaded the keypair in the downloads folder of type .pem and I moved to the keypair to the DevOps folder for easy access.

---

## Set up VS Code

### What I did in this step

In this step, I am going to install VScode which is a tool that lets us write and edit code and it's free. I am going to setup the terminal and update the settings of my private key.

### What is VS Code?

 VS code is an IDE that I am using to write and edit webapp code.  It also has handy expansions that directly connect to an EC2 instance so that I can write and edit code that lives inside the EC2 instance. 

I am installed VS Code to write and edit the web app code. I am going to make the most out of the ablity to connect directly to EC2 instance.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is where you send instructions to your computer using text instead of clicks. The first command I ran for this project is cd C:\Users\Gawthaman\Desktop\DevOps and it navigates to the DevOps folder in Desktop. 

### Updating file permissions

I also updated my private key's permissions by icacls "nextwork-keypair.pem" /reset icacls "nextwork-keypair.pem" /grant:r "Gawthaman:R" icacls "nextwork-keypair.pem" /inheritance:r
This command gives to access the file so that i could connect to EC2

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

### What I did in this step

In this step, I will try to connect to EC2 instance. Once I have connected to EC2 instance, I can start setup the web app code.

### Connecting to EC2

To connect to my EC2 instance, I ran the command "ssh -i C:\Users\Gawthaman\Desktop\DevOps/nextwork-keypair.pem ec2-user@ec2-13-204-77-77.ap-south-1.compute.amazonaws.com" , this command sets up the connection between the local computer and EC2.

### This command required an IPv4 address

A server's IPV4 DNS is like a public address that identifies where the server lives in the cloud. In my case EC2 instance's IPv4 DNS is useful information to give to our local computer - it lets our computer where to find the EC2 instance I launched.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

### What I did in this step

In this step, I am going to install Apache Maven on your EC2 instance and installing Amazon Corretto 8, a version of Java because both tools are important for setting up for my  java web app from scratch.

### Why I'm using Maven

Apache Maven is a tool that helps to create and organizing java projects. It comes with a lot of use cases, like being a package manager and the tool uses architypes for splitting up the projects like web apps.

Maven is required in this project because I want to use its ablity to split up web app using architypes. I am going to setup the Java web app using the web app architypes.

### Why I'm using Java

Java is a programming language that I am going to build the web app project. It is a popular and versatile choice and using to develop all different kinds of applications i.e web applications and enterprise systems.

Java is required in this project because it lays foundation for the writing my web app code. It is needing to know a language inorder to speak it. Maven also needs java in order to work the web app project that I am doing.

---

## Create the Application

### What I did in this step

In this step, I am going to create a web application inside AWS EC2 instance with Maven and Java

### Creating the Java web app

I generated a Java web app using the command mvn "archetype:generate" command specifically tells Maven to create a new project from a template. This command sets up a basic structure the project, and not needed to start it from scratch.

### Installing Remote - SSH

I installed Remote - SSH, which is the extension of VS code. This extension lets us connect to VScode directly to a remote server like an EC2 instance! 

### SSH configuration details

Configuration file details required to set up a remote connection include the host(i.e EC2 instance address), the identity file(i.e the location of the private key), and the user(the user that logging into the AWS EC2 instance).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

### Exploring the project structure

Using VS Code's file explorer, I could see a bunch of folders and subfolders that define the web app. Folders can be expanded by clicking on arrow button.

Two of the project folders created by Maven are src and webapp, which define the web app. These folders define different parts of the web app for e.g resources sub folder stores the connection details, webapp sub folder stores the web app details.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

### What I did in this step

In this step, I am connecting VS code with the EC2 instance. This is different from connecting the terminal(i.e local computer of the instance).

### Updating the web app

index.jsp is the file in the web app that defines both HTML element (i.e static element that go into web app's page) as well as my code for generating dynamic content  (i.e the content that is always changing).

I edited index.jsp by adding the HTML code by also saying "Hello This is DevOps project 1" and also added a paragraph (i.e some text that says "This is my web application working!").

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

### Additional improvements

### Terminal vs IDE

### Verifying my work

---

---
