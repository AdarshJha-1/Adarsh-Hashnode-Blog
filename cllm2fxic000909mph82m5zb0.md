---
title: "🚀📅 Day 22 DevOps Challenge - 🚀 Getting Started with Jenkins: Automate Your CI/CD Workflow!"
seoTitle: "day-22-devops-challenge-getting-started-with-jenkins-automate-your-cic"
seoDescription: "day-22-devops-challenge-getting-started-with-jenkins-automate-your-cicd-workflow"
datePublished: Tue Aug 22 2023 08:50:33 GMT+0000 (Coordinated Universal Time)
cuid: cllm2fxic000909mph82m5zb0
slug: day-22-devops-challenge-getting-started-with-jenkins-automate-your-cicd-workflow
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692694054859/8df80cd5-cb87-4bd9-b13d-871aa65a37b0.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692694218126/f73f1935-8ef8-4c2e-ad51-d899b939bc76.jpeg
tags: software-development, web-development, devops, jenkins, 90daysofdevops

---

## **Getting Started with Jenkins: Automate Your CI/CD Workflow** 🚀

Are you ready to take your software development and deployment process to the next level? If you've already set up Linux, Git, GitHub, and Docker, it's time to dive into the world of Continuous Integration and Continuous Delivery (CI/CD) using Jenkins, a powerful automation tool. 😎

## **What is Jenkins?**

Jenkins is a remarkable open-source CI/CD automation tool built using Java. It's designed to streamline your development workflow by automating tasks such as building, testing, and deploying your software projects. Jenkins operates as a server and enables developers to focus more on coding and less on manual processes. It's a game-changer for DevOps practices. 🔧

## **The Magic of Jenkins Automation** ✨

Imagine a world where you can initiate complex development workflows, run tests, and deploy applications without lifting a finger. Jenkins makes this possible through its robust automation capabilities. Here's a glimpse of what it can do:

1. **Continuous Integration (CI)**: Jenkins promotes a collaborative development environment by continuously integrating code changes from multiple developers. It ensures that changes made to the codebase don't break existing functionality by automatically building and testing the code. 🔄
    
2. **Continuous Delivery and Deployment (CD)**: With Jenkins, you can automate the delivery and deployment of your software to various environments, such as staging and production. This ensures a consistent and reliable deployment process, reducing the chances of errors and downtime. 🚚
    
3. **Pipelines**: Jenkins organizes your automation tasks into pipelines. A pipeline is a sequence of stages that define the flow of your CI/CD process. These stages can include building, testing, packaging, and deploying your software. Jenkins pipelines are highly customizable, allowing you to tailor the process to your project's needs. 🛠️
    

## **The Power of Plugins** 🔌

Jenkins's extensibility comes from its rich ecosystem of plugins. Plugins allow you to integrate Jenkins with various tools and services that you use in your development process. Need to use Git for version control? There's a plugin for that. Want to deploy your application to Amazon Web Services (AWS)? There's a plugin for that too.

## **Why Jenkins Matters** 🌟

In the age of instant gratification, automation is a necessity. Jenkins frees developers from manual, repetitive tasks, enabling them to focus on innovation and creativity. Here's why Jenkins is crucial:

1. **Efficiency**: Jenkins speeds up your development cycle by automating tasks that would otherwise consume valuable time and resources. ⏩
    
2. **Reliability**: Automation reduces human error, leading to consistent and reliable deployments. 🧐
    
3. **Scalability**: As your projects grow, Jenkins can handle the increased complexity of managing and automating your workflows. 📈
    
4. **Flexibility**: Jenkins adapts to your development process, not the other way around. You can customize and fine-tune your automation to fit your specific requirements. 🧩
    

## **Installation** 🛠️

Before you can harness the power of Jenkins on Ubuntu Linux, you need to ensure that you have Java properly installed on your machine, as Jenkins runs on the Java platform. Follow these steps to install Java and Jenkins:

1. **Installation of Java**: Jenkins requires Java in order to run. We will use OpenJDK, a popular Java implementation. Open a terminal and execute the following commands to update your package repositories, install OpenJDK 17, and check the installation:
    
    ```bash
    sudo apt update
    sudo apt install openjdk-17-jre
    java -version
    ```
    
    You should see output similar to the following:
    
    ```bash
    openjdk version "17.0.7" 2023-04-18
    ```
    
2. **Installation of Jenkins**: To install Jenkins, you'll first need to add the Jenkins repository and its GPG key to your system. Run the following commands in your terminal to add the key and repository, then update your package repositories and install Jenkins:
    
    ```bash
    curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
      /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
      https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
      /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692692497498/5f1206a6-b6c6-4c75-b655-74240af239ac.png align="center")
    
3. **Starting Jenkins**: Once Jenkins is installed, start the Jenkins service and enable it to start on boot:
    
    ```bash
    sudo systemctl start jenkins
    sudo systemctl enable jenkins
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692692550264/4b1aa64b-aade-4e72-af9b-eca1f2d39549.png align="center")
    
4. **Access Jenkins**: Jenkins runs on port 8080 by default. Open your web browser and navigate to [`http://localhost:8080`](http://localhost:8080). You'll be prompted to enter an initial admin password which can be found on your system:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692692616605/bfe992af-0b09-4e16-9eb3-9be796e80f51.png align="center")
    
    ```bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692692947622/a9e59f1f-989e-4838-8f0c-8158c41fc845.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692692984526/32689cef-915b-408d-827e-d6bb79d92d3a.png align="center")
    
    Follow the on-screen instructions to complete the Jenkins setup.
    

With Java and Jenkins properly installed and configured, you're ready to explore the world of automated CI/CD with Jenkins! 🚀Now that you understand the essence of Jenkins and why it's a must-have tool in your development arsenal, you're ready to explore the nitty-gritty of setting up and configuring Jenkins pipelines. Get ready to supercharge your development workflow and embrace the world of automated CI/CD. 😃🛠️

## **Creating a Freestyle Pipeline: Saying "Hello World!"**:

Let's dive into the world of Jenkins by creating a simple freestyle pipeline that prints "Hello World!" Here's how:

1. **Install Jenkins**: Ensure you have Jenkins installed on your system by following the installation steps mentioned earlier in the blog.
    
2. **Access Jenkins Dashboard**: Open your web browser and go to [`http://localhost:8080`](http://localhost:8080) to access the Jenkins dashboard.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692693272209/a0bafb23-076a-4971-b168-993e8c3b284c.png align="center")
    
3. **Create a New Freestyle Project**:
    
    * Click on "New Item" on the left-hand side.
        
    * Enter a name for your project (e.g., "HelloWorldPipeline").
        
    * Choose "Freestyle project" and click "OK".
        
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692693349288/1327235c-1936-4f82-8365-def026af7c51.png align="center")
        
4. **Configure the Pipeline**:
    
    * In the project configuration, under the "General" section, you can provide a description of your pipeline.
        
    * Scroll down to the "Build" section.
        
    * Click on "Add build step" and choose "Execute shell" (since we're using Linux).
        
5. **Writing the Shell Script**:
    
    * In the "Command" box, enter the following simple shell command:
        
        ```bash
        echo "Hello World!"
        ```
        
6. **Save and Run**:
    
    * Click on "Save" to save your pipeline configuration.
        
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692693477572/b7f27179-de6d-471b-ac32-19b904512c08.png align="center")
        
    * You'll be redirected to the project page.
        
    * Click on "Build Now" to trigger the pipeline.
        
7. **View the Console Output**:
    
    * Once the pipeline runs, click on the build number under "Build History".
        
    * On the build page, click on "Console Output" to see the output of your pipeline.
        
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692693627311/017caf68-4f99-470d-aa2c-32feb2bea1ed.png align="center")
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692693653962/9c318a17-05a1-4ab1-97e2-0c530ed126a9.png align="center")

Congratulations! You've just created and run your first Jenkins pipeline. It might seem like a small step, but it's a glimpse into the powerful world of CI/CD automation that Jenkins brings to the table. From here, you can build more complex pipelines to automate your entire development process.