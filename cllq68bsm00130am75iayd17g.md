---
title: "🚀📅 Day 24 DevOps Challenge - Unleashing Jenkins Power: Seamlessly Build, Deploy, and Automate with WebHooks 🚀"
datePublished: Fri Aug 25 2023 05:47:41 GMT+0000 (Coordinated Universal Time)
cuid: cllq68bsm00130am75iayd17g
slug: day-24-devops-challenge-unleashing-jenkins-power-seamlessly-build-deploy-and-automate-with-webhooks
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692942318154/b741ec25-0f41-45fa-b7e1-4e0cb95f470b.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692942374554/ceaa18ac-3799-40a8-99a4-2160497525f2.avif
tags: docker, web-development, devops, ci-cd, 90daysofdevops

---

## **⚓Task-01:** 🚀 **Getting Started with Jenkins and GitHub for CI/CD using GitHub Webhooks** 🌐

**Step 1: Fork the Repository**

* Go to [**https://github.com/LondheShubham153/node-todo-cicd**](https://github.com/LondheShubham153/node-todo-cicd)
    
* Click on the "Fork" button in the upper-right corner to create your own copy of the repository.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692935641889/3f873bb5-037f-4465-9117-602067a3e162.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692935683268/23a4fbc5-cee3-4005-bb5d-a67ed4ff0f01.png align="center")

**Step 2: Create a Freestyle Project in Jenkins**

* Log in to your Jenkins dashboard.
    
* Click on "New Item" to create a new project.
    
* Enter a name for your project and select "Freestyle project," then click "OK."
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692938174278/34eab7eb-8c3c-46a2-98cf-8473bb5b6c25.png align="center")

**Step 3: Configure Repository URL**

* In the project configuration, scroll down to the "Source Code Management" section.
    

* Select "Git" and paste the URL of your forked repository.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692935951133/68995aa2-e8b7-49c3-8a7f-8ff2c9b608ad.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692936136312/8fed72f7-db7c-42a1-8ef6-96825d93a908.png align="center")

**Step 4: Set Up Source Code Management**

* In the "Build Triggers" section, select "GitHub hook trigger for GITScm polling." This will enable Jenkins to listen for GitHub webhook events.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692936188638/e9bc68f8-17f5-40a2-bd33-fcf9ecb09942.png align="center")

**Step 5: Connect Jenkins to the GitHub Repository**

* Go back to your Jenkins project's dashboard.
    
* In the left-hand menu, click on "Configure" to edit the project settings.
    
* Scroll down to the "Build" section and click on "Add build step."
    
* Choose "Execute shell" and enter the command that you want Jenkins to execute after the job is built. This could be your build and deployment script.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692936371742/63b143be-4a27-49b8-a073-95ed84f9208a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692936931843/b3f015b6-addf-4df4-9ee6-9e9a40da559d.png align="center")

**Step 6: Configure Webhook in GitHub**

* Open your forked GitHub repository.
    
* Go to the "Settings" tab.
    
* In the left-hand menu, select "Webhooks" and click on the "Add Webhook" button.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692937188424/d1608b10-72cc-4f7c-a99d-a5b064f05270.png align="center")

* In the "Payload URL" field, enter the Jenkins URL followed by `/github-webhook/`. This is where Jenkins will listen for webhook events.
    
* Under "Which events would you like to trigger this webhook?" select the events that should trigger the webhook. For CI/CD purposes, you might choose "Push" events.
    
* Click "Add webhook" to save the configuration.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692938808142/b18d389d-90b6-4fd1-a343-4afaa736e22b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692938846749/1c6b28de-7642-43fc-9241-49ae85dd5d56.png align="center")

**Step 7: Test the Webhook**

* To test the webhook, make a small code change in your forked GitHub repository (e.g., edit a file, add a new line).
    
* Commit and push the change to the repository.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692938928155/c0fa750d-be02-45f7-9704-bc18ab8a29b5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692938957182/00aa2fd5-abc4-445c-9370-621202380bc3.png align="center")

**Step 8: Observe Automatic Triggering**

* When you push the code change, GitHub will send a webhook payload to the Jenkins webhook URL.
    
* Jenkins will detect this payload and trigger the job you configured.
    
* Go to the Jenkins dashboard and observe the job running automatically based on the webhook trigger.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692939523557/d4c5a21a-b1e7-495a-95a5-344f3625dd16.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692939535202/2c9e3466-95aa-43ec-b8fd-162dbecba90d.png align="center")

With these steps, you've successfully set up Jenkins with GitHub for CI/CD using GitHub webhooks. Now, whenever you push code changes to your GitHub repository, Jenkins will automatically run your specified build and deployment steps.

## 🛠️ **Task 2: Seamless Application Deployment using Webhooks and Docker Compose** 🚀

**Step 1: Setting Up Jenkins with GitHub Webhook**

1. Follow the steps mentioned in your previous Task 1 to set up Jenkins with GitHub webhook integration. This includes forking the repository, configuring the Jenkins job, and setting up the webhook in your GitHub repository settings.
    

**Step 2: Configure Docker Compose and Deployment Script**

1. In your Jenkins job configuration, locate the "Execute shell" build step.
    
2. Modify the execute shell command to include Docker Compose commands for deploying your application. For instance:
    
    ```bash
    # Stop and remove the existing containers
    docker-compose down
    
    # Pull the latest changes from the repository
    git pull origin master
    
    # Build the Docker images
    docker-compose build
    
    # Start the application using Docker Compose
    docker-compose up -d
    ```
    
    Adjust the commands according to your application's needs and your Docker Compose setup.
    
3. Save the Jenkins job configuration.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692940397600/f6b4727c-79c5-4338-9dfe-f01ed3988c9b.png align="center")

**Step 3: Test the Webhook and Deployment**

1. Make a small code change in your GitHub repository (like modifying a file or adding a new line).
    
2. Commit the change to your repository.
    

**Step 4: Automated Deployment**

1. With the webhook in place, GitHub will send a payload to Jenkins upon receiving your commit.
    
2. Jenkins will trigger the configured job automatically.
    
3. The job's execute shell commands will run, which includes stopping any existing containers, pulling the latest code changes, rebuilding images, and restarting the application using Docker Compose.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692941007666/0bc10bc9-b1d8-42f1-8d2e-f195f8a8762f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692941019139/fa9c91c6-e5a6-4f36-ac87-bfe8ea2ba732.png align="center")

By following these steps, you've set up a continuous deployment process using webhooks, Jenkins, and Docker Compose. Your application will be automatically deployed whenever you make changes to the GitHub repository and trigger the webhook event. Always make sure to adapt the commands and scripts to match your specific project's requirements.

### 🎉 **Final Thoughts**

Webhooks act as messengers, letting GitHub talk to external services (such as Jenkins) about what's happening in a repository. These happenings could be anything from pushing code to creating pull requests or updating issues.

When you set up a webhook in your GitHub repository settings and share your Jenkins server's URL, you're essentially creating a bridge that allows GitHub to send important updates to Jenkins whenever interesting events occur. 💌