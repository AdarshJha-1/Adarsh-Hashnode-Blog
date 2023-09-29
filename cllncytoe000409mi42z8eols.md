---
title: "🚀📅 Day 23 DevOps Challenge - Jenkins Freestyle Project for DevOps Beginners 🛠️🚀"
seoTitle: "day-23-devops-challenge-jenkins-freestyle-project-for-devops-beginners"
seoDescription: "day-23-devops-challenge-jenkins-freestyle-project-for-devops-beginners"
datePublished: Wed Aug 23 2023 06:32:57 GMT+0000 (Coordinated Universal Time)
cuid: cllncytoe000409mi42z8eols
slug: day-23-devops-challenge-jenkins-freestyle-project-for-devops-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692771942660/0c3dac9a-9a9e-4a10-aee5-05cec2f70707.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692772359764/a0641de4-a5a2-48d9-bd80-b75a4fb40ee2.png
tags: docker, web-development, jenkins, 90daysofdevops, devps

---

# Introduction

In the exciting world of DevOps, where the magic happens in software development, we're going to explore a superhero tool called Jenkins! 🦸‍♂️ Imagine Jenkins as your personal helper that automates tasks and makes your life easier. Let's dive into the Jenkins Freestyle Projects and see how they fit into the puzzle of CI/CD for beginners like you!

# **CI/CD: The DevOps Super Duo** 🤖🚀

Picture CI (Continuous Integration) as your trusty sidekick that brings all the superheroes (developers) together to work on a single mission: building awesome software. It makes sure that everyone's code plays nicely together and catches bugs early to save the day 🐞🦠. CD (Continuous Delivery) swoops in after CI and ensures that your software is ready to fly into the world without any hiccups 🚀.

# **Meet the Build Jobs** 🏗️

Think of build jobs as the different steps in a secret recipe to create a magical potion (your software). These steps include mixing ingredients, stirring, and finally pouring out a perfect potion. In Jenkins, we have different types of build jobs. Today, we're focusing on the "Freestyle Projects," which is like your canvas for creating your magical spells!

# **Freestyle Projects: Your DevOps Playground** 🎮🔧

1. **Build and Compile** 🛠️: Imagine this as creating a blueprint for your software. Jenkins takes your code and turns it into something the computer can understand and run. No more gibberish!
    
2. **Testing Magic** 🧪✨: Here, Jenkins becomes a skilled magician. It runs tests to make sure your software works as expected. Like a spell checker for your code!
    
3. **Saving Artifacts** 📦🔮: Artifacts are like treasures Jenkins helps you collect after the spell is cast. These could be your software, special documents, or even a recipe to recreate the potion!
    
4. **Custom Adventures** 📜🔍: With freestyle projects, you're the boss! You can add your own instructions, like a wizard adding personal touches to a spell. Got a unique task? Jenkins can handle it!
    
5. **Deploying with Confidence** 🚚🌎: Think of deployment as sending your magical potion into the real world. Jenkins helps you do this safely, making sure your potion works its charm everywhere.
    

# **Time to Embrace Your DevOps Powers!** 🦹‍♀️🚀

Jenkins Freestyle Projects are like the training wheels for your DevOps journey. They empower you to automate tasks, catch bugs, and sprinkle your magic across the software world. With CI and CD as your dynamic duo and Jenkins as your trusty sidekick, you're ready to conquer the world of DevOps, one spell (or code) at a time! 🌟🔥

### Task-01: Jenkins Freestyle Project for Building and Deploying Your App

Hello there, DevOps Explorer! Ready to take your app to the next level with Jenkins? Let's dive into a simple yet enchanting task where you'll create a Jenkins freestyle project to build and deploy your app using Docker.

**Step 1: Prepare Your Magic Workshop**

1. **Log into Jenkins** 🌐: Access your Jenkins dashboard – your hub for all things magical.
    
2. **Create a New Freestyle Project** 🏗️: Click "New Item," give your project a name, and select "Freestyle project."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692768051235/95922a13-9298-4714-a3fb-e755706e10ab.png align="center")
    

**Step 2: Configure the build steps:**

* In the Source Code Management section, use the GitHub Repository URL to access the Dockerfile
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692769851348/d724b52c-8239-4203-be8d-c91041de602d.png align="center")
    

**Step 3: Casting the Build and Deploy Spell**

1. **Configure Build Step** 🔧: In your project's configuration, scroll down to the "Build" section.
    
2. **Add a Build Step** ➕: Click "Add build step" and choose "Execute shell" or "Execute Windows batch command," depending on your system.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692768145632/be4cffa0-cf3c-4ffb-a1a7-3934f011724b.png align="center")
    
3. **Build the Container** 🏗️: Inside the shell command box, enter:
    
    ```bash
    cd /var/lib/jenkins/workspace/item-name
    docker build -t notes-app .
    echo "Image created"
    ```
    
    This command crafts your app's container image.
    
4. **Add Another Build Step** ➕: Click again and choose the same command type.
    
5. **Summon the Container** 🧞‍♂️: In the command box, enter:
    
    ```bash
    echo "Docker images"
    docker images
    echo "------------------------------------"
    docker run -d -p 8000:8000 notes-app:latest
    echo "Container is created and running"
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692770125413/ecd320fb-750e-49a1-bd64-dc142ce509c8.png align="center")
    
6. This command starts your app's container, making it accessible at port 8000.
    

**Step 4: Unleash the Magic**

1. **Save Your Spell** 💾: Hit "Save" to seal your freestyle project's enchantment.
    
2. **Cast Your Spell** 🪄: Click "Build Now" to invoke your project's magic. Watch as Jenkins weaves its automation to build and deploy your app.
    
3. **Witness the Enchantment** ✨: Check the console output – a magical scroll revealing the progress of your spell casting.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692769415913/e46d44b1-689f-4071-b704-57dc4ae5fd01.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692769465340/cb3f0173-a4c8-4298-a86e-3d38f38e3246.png align="center")

**Conclusion: Your App, Up and Running with Jenkins!**

Congratulations, you've just summoned the power of Jenkins to build and deploy your app effortlessly! With this simple freestyle project, you've taken a big step into the world of DevOps magic. Keep exploring Jenkins, and tweaking your spells, and your app will continue to thrive and amaze. The journey has just begun! 🚀🔮

### Task-02: Managing Docker Compose with Jenkins 🐳🚀

**Step 1: Create a New Jenkins Project**

1. Log in to your Jenkins dashboard.
    
2. Click on "New Item" to create a new project.
    
3. Enter a name for your project, choose "Freestyle project," and click "OK."
    

**Step 2: Configure Jenkins Project**

1. On the project configuration page:
    
    * Under "General," you can provide a project description.
        
    * Under "Source Code Management," select the appropriate option if you're using version control.
        
    * Under "Build Triggers," you can choose when to trigger the build (e.g., after a push to your repository).
        

**Step 3: Configure Build Steps**

1. In the "Build" section, click "Add build step" and choose "Execute shell."
    
2. In the shell command box, enter the following command to start the containers using Docker Compose:
    
    ```bash
    cd /path/to/your/docker-compose/folder
    docker-compose up -d
    ```
    
3. Add another build step for the cleanup process:
    
    ```bash
    cd /path/to/your/docker-compose/folder
    docker-compose down
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692771403459/1bed572c-92d6-4996-8e6c-c68303d9b1d8.png align="center")

**Step 4: Save and Run the Jenkins Project**

1. Click "Save" to save your Jenkins project configuration.
    
2. You can manually run the project by clicking "Build Now" or wait for the configured triggers to initiate the build.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692771727616/cb2b737e-1f20-422c-a7bf-fc07ee1eb1ac.png align="center")

**Step 5: Verify the Build Steps**

When the Jenkins project runs, it will execute the specified commands. It will start the containers using the `docker-compose up -d` command and then stop and remove them using the `docker-compose down` command.

Please replace `/path/to/your/docker-compose/folder` with the actual path to the directory containing your `docker-compose.yml` file.

Remember to ensure that Jenkins has the necessary permissions to execute Docker commands and access the Docker Compose file. Additionally, make sure Docker and Docker Compose are properly installed on the Jenkins server.

Always exercise caution when using automated build and cleanup processes, especially in production environments. Test thoroughly in a controlled environment before applying to critical systems.