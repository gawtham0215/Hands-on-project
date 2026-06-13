<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Deploy an App with Docker

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-eb)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eb_c4df13c84)

---

## Introducing Today's Project!

### What is Docker?

Docker is a platform that enables developers to build, test, and deploy applications using containers. I used Docker to create Docker image files and launched web application using Docker image.

### One thing I didn't expect...

One thing you didn't expect in this project is using AWS Elastic Beanstalk to see the output of updated web application by not using the Docker images.

### This project took me...

I took two hours to complete this project including documentation.  

---

## Understanding Containers and Docker

### Containers

Containers are simply an isolated process with all of the files it needs to run. If you run multiple containers, they all share the same kernel, allowing you to run more applications on less infrastructure because containers package up everything.

A container image is template/blueprint for creating containers. Containers spawned/created from the same container image will behave in the same way, which helps with developers in a team having a unified experience when they running an application.

### Docker

Docker is a platform for creating and managing containers. Docker makes working with containers easy! Docker Desktop is a software for using/ interacting with docker. Docker Desktop makes working with Docker itself easy. 

The Docker daemon is the engine that actually does the thing when you run Docker commands. In other words Docker daemon is a background process that manages the Docker containers on your computer. It takes commands from the Docker client.

---

## Running an Nginx Image

Nginx is a web server/ a software that helps with serving web content. Nginx is often refered to as a proxy server which means it helps with distributing traffic to the application across the instances running to your application.

The command I ran to start a new container was docker run. I also set the flags -d -p 80:80 nginx, which means I am running the container in the background (-d) and matching port 80 in host computer to the containers port 80 ( -p 80:80).


![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eb_6245f5bb10)

---

## Creating a Custom Image

The Dockerfile is a set of instructions that tells Docker how to build your custom container image.

My Dockerfile tells Docker three things, first the container image uses the latest version of Nginx container image at its base. Then making modifications on this base by saying that I want the Nginx web server to our customised web page.

The command I used to build a custom image with my Dockerfile was Docker build. The '.' at the end of the command means the Docker can find the Dockerfile in the current directory i.e the Compute folder in the desktop.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eb_4c741d1913)

---

## Running My Custom Image

There was an error when I ran my custom image because i tried to map port 80 with the new container's port 80. I resolved this by typing commands 'docker ps --filter "publish=80", "docker stop {container_id}" and "docker run -d -p 80:80 my-web-app".

In this example, the container image is the template for creating the new container that running the Nginx server that serves the index.html file. The container is actually the software that's running on an Nginx web server with those specifications.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eb_74b5c3d619)

---

## Elastic Beanstalk

💡 What is Elastic Beanstalk?
Elastic Beanstalk is a service that makes it easy to deploy cloud applications without worrying.Elastic Beanstalk handles things like Capacity provisioning, Load balancing, Auto-scaling and Application health monitoring.

Deploying my custom image with Elastic Beanstalk took me to the updated content of index.html file and saw the changes in the output without using Docker image.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eb_26d5573b23)

---

## Deploying App Updates

---

---
