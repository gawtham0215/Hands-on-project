<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launch a Kubernetes Cluster

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-eks1)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Launch a Kubernetes Cluster

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eks1_e5f6g7h8)

---

## Introducing Today's Project!

In this project, I will deploy my first Kubernetes cluster using Amazon EKS. This is because EKS is AWS service for deploying Kubernetes clusters in the cloud. I also get to learn cool tools like eksctl and CloudFormation.

### What is Amazon EKS?

### One thing I didn't expect

### This project took me...

---

## What is Kubernetes?

Kubernetes is a tool for automating to managing the containers/containerize applications aka container orchestration. Companies and developers use Kubernetes to deploy and manage large scale containerized applications.

I used eksctl to create a Kubernetes cluster using the command line. The "eksctl create cluster" command I ran defined the name of cluster its node group name and node size settings. I also defined the region and the instance type of EC2.

I initially ran into two errors while using eksctl. The first one was because of not having eksctl installed yet. The second one was because of EC2 instance did not have permissions to my AWS account and services yet.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eks1_ff9bfc221)

---

## eksctl and CloudFormation

CloudFormation helped create my EKS cluster because eksctl uses CloudFormation under the hood to actually create the cluster when I run the eksctl create command. It created VPC resources because creating EKS cluster in my default VPC will create compatiblity issues.

There was also a second CloudFormation stack for a nodegroup. The difference between a cluster and node group is "cluster" is made up of nodes (the servers that actually run your containers) and a control plane (the brain that decides things like when to create or shut down containers).

Within your cluster, the nodes are organized into node groups. "Node groups" lets to manage multiple nodes more easily by grouping them together, so I can control settings like instance type and resource limits for the whole group instead of adjusting each node individually. This makes it much simpler to scale and configure nodes for specific tasks.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eks1_w3e4r5t6)

---

## The EKS console

I had to create an IAM access entry in order to see the nodes in our new node group. An access entry is the mapping of AWS IAM policies to Kubernetes access control system  I set it up by using the Access Entry P age within the Elastic Kubernete Service management console.

It took 20 minutes to create my cluster including demo time. Since I'll create this cluster again in the next project, maybe this process could be sped up if I used templates e.g Terraform or CloudFormation and dependencies ahead. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-compute-eks1_e5f6g7h8)

---

## EXTRA: Deleting nodes

---

---
