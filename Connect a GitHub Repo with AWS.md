<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a GitHub Repo with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-github)

**Author:** Gawthaman M N  
**Email:** gawthaman15021999@gmail.com

---

## Connect a GitHub Repo with AWS

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-github_dd9d254e)

---

## Introducing Today's Project!

Today I am here to set up a Git repository for my web app's code. This is project TWO in 7 day DevOps challenge. By the end of this project, the code that I written for java web app will be stored securely in Github .

### Key tools and concepts

Services I used were EC2, EC2 instance key pair and VScode terminal and a Github account . Key concepts I learnt include setting up a Git repository, differences between Git and Github and the commands for staging, saving and pushing the code. 

### Project reflection

This project took me approximately 2.5 hours including documentation. The most challenging part was updating the code using Github username and password and overcome the error using Git push command  It was most rewarding point to see the output.



I did this project to learn more about the Github and this is  day TWO of 7 day DevOps challenge. Excited to have a Github repository that stores the web application project's source code. 

This project is part TWO of a series of DevOps projects where I am building a CI/CD pipeline! I will be working on the next project of Storing  Dependencies in CodeArtifact  of 7 day DevOps challenge.

---

## Git and GitHub

Git is a version control system which means it's used to track changes that I make in the code. It is also incredibly helpful for collaboration with GIT. I installed Git using the commands "sudo dnf update -y and sudo dnf install git -y".



GitHub is a platform that lets us to store, share and collaborate on our code! Git is the tool for tracking changes and GitHub use Git as a tool for version control. I am using GitHub in this project to store the web app's code that I wrote.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-github_efaadbf7)

---

## My local repository

A Git repository is like a online folder that I can use to store the web app's code and all versions of code. Think it of as the go-to place for all the code and updates and changes related to a specific project.

'git init' is a command that initialises the Git in the repository. I ran git init in the web app project folder which tells the terminal that I want to start tracking  changes locally.

After running git init, the response from the terminal was
I initialized Git and by default I am using 'main' branch. A branch in Git is like a version of your code that i make changes over a branch and then merge those changes into the main branch. 

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-github_7bf21bae)

---

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was "git add."
A staging area in Git is like a place to review all changes made to the code so that I can decide what changes i would like to save in a commit.

### git commit

The second command I ran was "git commit" which is the command for saving changing changes in the staging area. Using '-m' means leaving the message for commit for e.g made changes in the index.jsp.

### git push

The third command I ran was "git push -u origin master". This command pushes the code changes that i saved to remote origin. '-u'  is a special flag that makes the remote origin the UPSTREAM repository.



---

## Authentication

When I commit changes to GitHub, Git asks for my credentials because Git needs to authenticate the code changes in the Github repository when I try to enter the password, to do this I need the rights to change the code in Github repository.

### Local Git identity

Git needs my name and email because it is a version control system which means it is used for tracking WHO made WHAT changes to a piece of code. To really identify the people that made x changes, Git needs to know the name and email ID. 

Running git log shows that by default, Git is saving the and changes to the username called "EC2 Default User" instead of actual name and details.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-github_9a27ee3b)

---

## GitHub tokens

GitHub authentication failed when I entered my password because support for password authentication was removed in 2021. There are too many risk associated with entering a password over terminal to Github, there are so more secure ways are available 

A GitHub token is 
I am using one in this project because 



I could set up a GitHub token by clicking on the github profile then click -> Developer settings at the navigation panel -> click on Personal access token -> click on token classic then click repo box under scope menu and click -> genenerate.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-github_fa11169d)

---

## Making changes again

I wanted to see Git working in action, so I run commands git add  and git diff --staged and I couldn't see the changes in my GitHub repo initially because I did not run the push command so that i did not see the changes.

I finally saw the changes in my GitHub repo after entering the commands 'git commit -m "Add new line to index.jsp"
git push'  and the Github username and personal token acees provided by Github account and the changes reflected in the Github account.

![Image](http://learn.nextwork.org/daring_azure_bold_octopus/uploads/aws-devops-github_6becb2bc)

---

## Setting up a READMe file

---

---
