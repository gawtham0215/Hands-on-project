<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Continuous Integration with CodeBuild

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codebuild-updated)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codebuild-updated_35588a47)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use AWS CodeBuild to automate the build process in the CI/CD pipeline. Building means compressing the web app's file into a single compressed file. I am doing this project to learn about CodeBuild.

### Key tools and concepts

Services I used were CodeBuild, CodeConnection, CodeArtifact, S3, EC2, GitHub and VSCode. Key concepts I learnt include build process, resolving buildspec.yml file and using CodeConnection to connect AWS and GitHub.

### Project reflection

This project took me approximately 2.5 hours including the documentation. The most challenging part was troubleshooting the CodeBuild artifacts and solve that by updating the IAM policy. It was most rewarding to CodeBuild message succeded.



This project is part four of a series of DevOps projects where I'm building a CI/CD pipeline! I will be working on the next project in upcoming day.

---

## Setting up a CodeBuild Project

CodeBuild is a continuous integration (CI) service, which means it helps me to compile and package code. Engineering teams use it because CI services automates the process - if CI doesn't exist engineer would have to do manually compile.



'My CodeBuild project's source configuration doesn't know where the web app's code lives! Source means the location of the code that CodeBuild will fetch, compile, and package into a file you can deploy. I am selected the GitHub app as the source.



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codebuild-updated_fewgrhte)

---

## Connecting CodeBuild with GitHub

There are multiple credential types for GitHub, like GitHub App, Personal Access Token and OAuth app. I used GitHub App because it is the most simple and secure way to set up a connection between GitHub and AWS - AWS handles all the credentials.

The service that helped connect the AWS environment with GitHub in AWS CodeConnections. CodeConnections lets to connect the environment with third party platforms, in this case I make sure that i have secure connections with GitHub. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codebuild-updated_a7c98e2d)

---

## CodeBuild Configurations

### Environment

My CodeBuild project's Environment configuration means environment set up for EC2instance it includes settings like provisioning model, compute, operating system, image and service role. These settings determine how a EC2 instance will build process

### Artifacts

Build artifacts are files/resources that get created as a part of CodeBuild build process and  important because they represents the artifacts that need to be used. My build process will create a compressed file. To store them, I created S3 bucket.

### Packaging

When setting up CodeBuild, I also chose to package artifacts into a zip file - this helps us with package management as file are organized in a single executable file. It also helps us to compress the size of compressed web app!

### Monitoring

For monitoring, I enabled CloudWatch Logs, which is a service and note down the commands that are running and errors that happen. This is useful for troubleshooting!

---

## buildspec.yml

My first build failed because a buildspec.yml file is needed because CodeBuild reads the buildspec.yml file like a step-by-step instruction manual. It goes through each phase in order - install, pre build, build, then post build - running commands.

'The first two phases in my buildspec.yml file installs java and get us access to CodeArtifact. The third phase in my buildspec.yml file compiles web app. The fourth phase in my buildspec.yml file packages the web app into a single compress file.



![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codebuild-updated_35588a47)

---

## Success!

My second build also failed, but with a different error that said logs BUILD, POST_BUILD and UPLOAD_ARTIFACTS fails and CodeBuild not get success. To fix this, I need to grant CodeBuild's IAM role the permission to access CodeArtifact.


To resolve the second error, I... When I built my project again, I saw errors  logs BUILD, POST_BUILD and UPLOAD_ARTIFACTS and solve that error using  policy "codeartifact-nextwork-consumer-policy" updated the policy in IAM console and got the output

To verify the build, I checked the phase details of all logs. Seeing the artifact tells me that CodeBuild was done successfully. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-codebuild-updated_d9cc6191)

---

## Automating Testing

---

---
