<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a CI/CD Pipeline with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codepipeline-updated)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Introducing Today's Project!

In this project, I'll demonstrate how to use CodePipeline to set up a CI/CD pipeline. CodePipeline will AUTOMATE the flow from GitHub all way to CodeDeploy and end of this project I will able to simply push a change to code and see updated web app.

### Key tools and concepts

Services I used were EC2, S3, GitHub, CodeBuild, CodeDeploy, CodePipeline and VSCode. Key concepts I learnt include setting up the pipeline, configuring the Source, Build and Deploy Stages, running and testing the CodePipeline.




### Project reflection

This project took me approximately 3 hours including documentation. The most challenging part was configure and setting up the CodePipeline and it was most rewarding to saw the updated web application in the website

---

## Starting a CI/CD Pipeline

AWS CodePipeline is a AWS DevOps tool that helps us create a workflow that automatically moves code from GitHub (my source code repository) all the way to deployment form CodeDeploy. CodePipeline makes sure the deployments are consistent, reliable.

CodePipeline offers different execution modes based on how we treat multiple runs of the same pipeline. I chose Execution mode and it determines how CodePipeline handles multiple runs of the same pipeline, other options include Queued and Parallel.

A service role gets created automatically during setup so that CodePipeline has the permission to access other AWS resources it needs to run your pipeline, such as S3 buckets for storing artifacts or CodeBuild for building your code.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_gdnhtm)

---

## CI/CD Stages

The three stages I've set up in my CI/CD pipeline are source stage, build stage, deploy stage. While setting up each part, I learnt about pipeline settings where CodePipline takes the source code from the source, building the web app and code deploy.

CodePipeline organizes the three stages into source, build and deploy.  In each stage, you can see more details on where it retrives source code from the source(GitHub), build the application code  by CodeBuild and deploy the code by CodeDeploy



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Source Stage

In the Source stage, which is about where source code from (GitHub),  the default branch tells CodePipeline which version of code exactly I want to use in this workflow. In production environment one can use different branches to represent version.



The source stage is also where you enable webhook events, which is like notification, whenever making a changes in the source code, the webhook event will detect the change and alert CodePipeline to trigger a new line. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_sergt)

---

## Build Stage

The Build stage sets up how to build the web app and make it ready for deployment. I configured the CodeBuild for build provider and to use input artifacts tells upward for source stage. The input artifact for the build stage is the SourceArtifact.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_j1k2l3m4)

---

## Deploy Stage

The Deploy stage is where I setup CodeDeploy for the deployment provider, it takes BuildArtifacts from CodeBuild. Application and deployment settings that I have defined in the deployment group.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_m4n5o6p7)

---

## Success!

Since my CI/CD pipeline gets triggered by command git commit -m "Update index.jsp with a new line to test CodePipeline" I tested my pipeline by "git add ." and git push command and waiting for CodePipeline to update the web app.

The moment I pushed the code change it reflects in the CodePipeline. The commit message under each stage reflects the code updated in the source code, build the code in the destination storage area and deploying the code change in the browser.

Once my pipeline executed successfully, I checked the deployment EC2 instance IPv4 DNS address by copying it and pasting it in a web browser and it displays the changes in the output. The changes in the output tells about the CodePipeline mechanism.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codepipeline-updated_e1f2g3h4)

---

## Testing the Pipeline

---

---
