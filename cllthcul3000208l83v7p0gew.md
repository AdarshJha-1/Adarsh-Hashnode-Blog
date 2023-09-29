---
title: "🚀📅 Day 26 DevOps Challenge - Exploring Jenkins Declarative Pipeline with Easy Steps! 🚀"
datePublished: Sun Aug 27 2023 13:22:27 GMT+0000 (Coordinated Universal Time)
cuid: cllthcul3000208l83v7p0gew
slug: day-26-devops-challenge-exploring-jenkins-declarative-pipeline-with-easy-steps
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693142409087/088b2fd6-edb6-40d6-a61f-fd8266e31b78.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693142537504/6dd726b9-8430-45b8-afec-3d5e8dd1a08f.webp
tags: software-development, web-development, devops, jenkins, 90daysofdevops

---

## **Introduction**

In the dynamic landscape of continuous integration and delivery, the Jenkins Declarative Pipeline emerges as a potent tool for orchestrating and optimizing software delivery processes. This mechanism streamlines the configuration of your continuous delivery pipeline, analogous to a meticulously crafted recipe guiding the journey from raw ingredients to a delectable final product, served piping hot! 🍲

## **🛠️ What is a Pipeline?**

Visualize a pipeline as a magical conduit that transforms raw code into a functional application through a well-defined sequence of steps. Like a conveyor belt in a factory, the pipeline ensures a seamless transition from code creation to building, testing, and ultimate delivery. 🌐

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692366162469/f7934ab5-0942-47ce-a3c1-2d54e682ece6.jpeg?auto=compress,format&format=webp align="left")

## **Declarative vs. Scripted Approaches**

### 📘 **Declarative Approach**

Think of the Declarative approach as following a recipe step by step, ensuring a consistent outcome. It simplifies the process and is particularly suitable for those new to the concept. It's like meticulously executing a culinary recipe to achieve a delectable dish. 🍳

### 🍴 **Scripted Approach**

In contrast, the Scripted approach empowers you with the freedom of a chef, allowing for unique and creative implementations. It's akin to crafting a dish with your personal flair, making it ideal for those well-versed in the process. 🧁

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692366230454/8f8ad9c0-b7ec-4bcd-ad8e-56971ccc3c5c.jpeg?auto=compress,format&format=webp align="left")

## **A basic example of a Declarative Pipeline:**

```bash
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build your application here
            }
        }

        stage('Test') {
            steps {
                // Run tests here
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your application here
            }
        }
    }
}
```

In this example, the pipeline has three stages: **Build, Test, and Deploy**.

Each stage contains a series of steps, and Jenkins will automatically manage the execution of these stages in the specified order.

## **The Imperative Need for a Pipeline**

### 🔧 **Automation**

Picture having an indefatigable robot toil through mundane and repetitive tasks, liberating you to focus on high-value endeavors. The pipeline acts as your automation companion, taking care of the tedious work. 🤖

### 🎯 **Consistency**

The Declarative Pipeline guarantees a consistent outcome every time you embark on your software journey. Similar to a perfected recipe, it ensures that your final product is consistently delightful and reliable. 🍰

### 📜 **Traceability**

One of its remarkable features is traceability, meticulously recording each step of your process. This feature empowers you to track changes and understand the evolution of your project over time. 📊

### 🔍 **Reproducibility**

Just like a cherished recipe enables you to recreate a beloved dish, the pipeline offers the ability to reproduce software builds reliably. This enhances project stability and confidence. 🥐

### ⚡ **Speed**

As an adept multitasker, the pipeline expedites development by simultaneously managing multiple tasks. It ensures efficient and timely execution of your software workflow. 💨

### 🚀 **Scale**

Whether you're catering to a grand event or a cozy gathering, the Declarative Pipeline effortlessly accommodates projects of varying sizes. Its scalability ensures seamless performance in diverse scenarios. 🍽️

# **Task-01 Create a Hello\_World job using the declarative pipeline.**

**Step 1: Launch an EC2 Instance named "JENKINS-SERVER"**

1. Launch an EC2 instance on your preferred cloud provider and name it "JENKINS-SERVER".
    

**Step 2: Install JAVA and JENKINS on the Jenkins-Server**

1. SSH into your EC2 instance.
    
2. Install Java and Jenkins on the instance.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693141462396/95d27a5f-9565-4696-9962-95b388d141ce.png align="center")

**Step 3: Access Jenkins Dashboard and Create a New Pipeline Job**

1. Open a web browser and navigate to `http://<public_ip>:8080` (replace `<public_ip>` with your Jenkins server's public IP).
    
2. Log in to the Jenkins dashboard.
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693141509332/ba02c722-9b8c-45ee-8e45-df2d0cbf4727.png align="center")
    
4. Click on "New Item."
    
5. Enter the name for the job as "HelloWorldPipeline."
    
6. Choose "Pipeline" as the project type and click "OK."
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693141597816/bb2e9f4c-b7cc-44de-b32c-634b77f2778e.png align="center")

**Step 4: Define Declarative Pipeline Script**

In the Pipeline section of the job configuration page:

```bash
pipeline {
    agent any

    stages {
        stage('Hello World') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
```

**Step 5: Build the Job**

1. Save the job configuration.
    
2. Click on "Build Now" to start the job.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693141821868/b2361d62-4c69-456b-a361-43f67a79bda8.png align="center")

**Step 6: View Build Status and Console Output**

1. Once the build completes, you'll see the build status on the job's page.
    
2. Click on the build number to view details.
    
3. Click on "Console Output" to see the complete output of the job.\\
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693141849225/9381e678-666f-49b1-9b84-551f3f5d584e.png align="center")
    

Please note that you'll need to adapt the steps and the provided Declarative Pipeline script to your actual setup and environment. Also, make sure you have Jenkins properly set up on your EC2 instance and have the necessary plugins installed for pipeline execution.

**Conclusion:** Jenkins Declarative Pipeline is your chef's assistant, taking your recipe (pipeline) and turning it into a delicious software dish. With automation, consistency, and traceability, you're on your way to becoming a master chef of software delivery! 🍔🚀