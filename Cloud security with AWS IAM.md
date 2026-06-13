<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use AWS IAM to control access and permissions in AWS account. I'm doing this project to learn about cloud security from absolute foundations.

### Tools and concepts

Services I used were AWS EC2 instance and IAM Key concepts include IAM users, policies, user groups and account aliases, how to launch an EC2 instance then how to tag a EC2 user and then how to log as an another user.

### Project reflection

This project took me approximately 2.5 hours to complete including output. The most challenging part was understanding IAM policy since it was written in JSON. It was most rewarding to see permission denied when intern try to delete production EC2.

---

## Tags

### What I did in this step

In this step, I will launch two Amazon EC2 instances so that we can increase NextWork's computing power and expecting more users and traffic inside NextWork website.

### Understanding tags

Tags are organisational tools that lets us label our resources. They are useful for grouping resources, cost allocation, and applying policies for all resources with the  same tag.

### My tag configuration

The tag I have used on my EC2 instances is called Env which stands for environment. The value I have assigned for the instances are production and development.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will use IAM policies to control access level of the new NextWork intern because it should have access to development environment (i.e development instance) but not the production environment.

### Understanding IAM policies

IAM Policies are like rules that determine who can do what in the AWS account.I have using policies to control who has access to production/development instance.

### The policy I set up

For this project, I have set up a policy using JSON.

### Policy effect

I have created a policy that that allows the policy holder to have permission to do anything want to any instance tagged with "development". The policy holder can also see any information for any instance but denied access to create/delete tags.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means whether or not the policy is allowing/denying action(i.e, effect) what the ploicy holder can or cannot do(i.e, action) and the specific AWS resources that the policy relates.

---

## My JSON Policy

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will setup an account Alias which is like a nickname for AWS account's console login. This is because an account alias makes it simpler for user to login.

### Understanding account aliases

An account alias is simply a nickname for AWS account instead of a long account ID. I can refer the account alias instead! 

### Setting up my account alias

Creating an account alias took 30 seconds it is a simple configuration in the IAM dashboard. Now, my new AWS console sign-in URL uses the alias account instead of my account ID!

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will setup two resources - IAM users and IAM users groups. This is because IAM users are like logins for people to access the AWS accounts and IAM user groups are like folders to manage the users having same level of user access.

### Understanding user groups

IAM user groups are like folders that collects IAM users so that apply permission settings at the group level.

### Attaching policies to user groups

I attached the policy and I created to this user group, which means any users inside this will automatically get the permissions attached to the NextWorkDevEnvironmentPolicy IAM policy.

### Understanding IAM users

IAM users are people or entities that have access/can login to AWS account.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is to Email sign-in instructions to the user while the second way is to download a .CSV file and sign in details inside.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed the is alredy denied access the panels on the main AWS dashboard. This was because I set up permissions to development EC2 instance so the intern would not have access to see even anything else.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will login into own AWS account as an intern and test access to the production and development instances because we want to make sure that the intern does not have the ability to affect the production environment.

### Testing policy actions

I tested my JSON IAM policy by attempting by stopping the production and development instance.

### Stopping the production instance

When I tried to stop the production instance I was met with an error. This was because the production instance is tagged with "production" label which is outside of the permission policy - intern are allowed only to do things in development instance.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance, I successfully saw the instance state change to stopping and then instance state stopped. This was because the permission policy allows the intern(users in the nextwork-dev group)to stop instances.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

### Understanding the IAM Policy Simulator

### How I used the simulator

---

---
