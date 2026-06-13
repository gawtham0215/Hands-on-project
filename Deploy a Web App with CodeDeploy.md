<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Deploy a Web App with CodeDeploy

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codedeploy-updated)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codedeploy-updated_val-27)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use CodeDeploy to deploy a web app. I am doing this project to learn about how deployments works, and how it can be automated using a combination of CodeDeploy and deployment scripts.

### Key tools and concepts

Services I used were CodeDeploy, CodeBuild, CodeArtifact, IAM, CloudFormation, EC2, S3, CodeConnection,VScode and GitHub. Key concepts I learnt include deployment, deployment groups, deployment scripts and importance of rebuild project before deploy.

### Project reflection

This project took me approximately 3 hours including documentation. The most challenging part was getting the output and troubleshooting of public IPv4 of deployment instance. It was most rewarding to see the output of web app project by solving it.

This project is part five of a series of DevOps projects where I'm building a CI/CD pipeline! Iwill be working on the next project in upcoming day.

---

## Deployment Environment

To set up for CodeDeploy, I launched an EC2 instance and VPC because they make up the production environment. I need to seperate the development environment (where I am writing the code) with the production environment (where I am delploy the code).

Instead of launching these resources manually, I used AWS CloudFormation. When I need to delete these resources created by our CloudFormation template I can simply delete the CloudFormation stack, automatically deleting the reourses inside the stack.

Other resources created in this template include networking resources like VPC, route tables, internet gateways and subnets. They are also in the template because production environment has specific requirements around the traffic enable or block.


![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codedeploy-updated_val-5)

---

## Deployment Scripts

Scripts are mini programs that helps to automate the running of commands. To set up CodeDeploy, I also wrote scripts to automate commands (i.e these are the commands that deployment EC2 instance needs to run inorder to host the web app).

install_dependencies will help the EC2 instance to install all the dependancies it needs to host a web app like Tomcat (web server).

start_server.sh is another script that's all about starting of two servers that I am using in the EC2 instance - one it starts Tomcat(responsible for running the java app) ; two it starts Apache(the web server responsible for handling web traffic).

stop_server.sh is a script that stops my Tomcat and Apache servers when they are no longer needed to serve the web app to the user.

---

## appspec.yml

Then, I wrote an appspec.yml file to give CodeDeploy the instructions for web app project. The key sections in appspec.yml are BeforeInstall, ApplicationStart and ApplicationStop.

I also updated buildspec.yml to tell CodeBuild that it should also package up the appsec.yml file to setup the scripts that we build inside the artifact(i.e the compressed app file).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codedeploy-updated_val-12)

---

## Setting Up CodeDeploy

A deployment group is a group of EC2 instances that you can deploy to and also the connection of settings that detrmine HOW you want to deploy your web app. A CodeDeploy application is simply a folder that holds deployment groups for the same app.

To set up a deployment group, you also need to create an IAM role to give CodeDeploy the permission to access the EC2 instances that it needs to coordinate, Otherwise CodeDeploy does not have access to deployment EC2 instance. 

Tags are helpful for identifying the instance that will be deploying the app. I used the tag "role:webserver" to automatically match the EC2 instance deployed with CloudFormation template.  
 



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codedeploy-updated_val-18)

---

## Deployment configurations

Another key settings is the deployment configuration, which affects how quickly and risky I am deploying the web app. I used CodeDeployDefault.AllAtOnce, so any changes CodeDeploy displays affects all the EC2 instances in the deployment group at once

In order to connect instance with CodeDeploy a CodeDeploy Agent is also set up to recive instructions from CodeDeploy and make sure that the commands in appsec.yml file are run.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codedeploy-updated_val-20)

---

## Success!

A CodeDeploy deployment is a specific update to our application that I am deploying to the users. The difference between deployment and deployment group is that group is like a settings file and and deployment is like a specific update to roll out.

I had to configure a revision location, which is the place where CodeDeploy looks to find your application's build artifacts.
My revision location was "s3://nextwork-devops-cicd-s3-codebuild/nextwork-devops-cicd-artifact".

To check that the deployment was a success, I visited the public IPv4 DNS of the deployment EC2 instances! I saw a live web app working and serving the web application to end users (which is awesomeeeee...).

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codedeploy-updated_val-27)

---

## Disaster Recovery

---

---
