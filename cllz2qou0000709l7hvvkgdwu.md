---
title: "🚀📅 Day 28 DevOps Challenge - 🚀 Jenkins Agents: Powering Scalable CI/CD Workflows 🏗️"
datePublished: Thu Aug 31 2023 11:19:55 GMT+0000 (Coordinated Universal Time)
cuid: cllz2qou0000709l7hvvkgdwu
slug: day-28-devops-challenge-jenkins-agents-powering-scalable-cicd-workflows
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693480705323/f2a128a0-d105-4d86-b592-22bae7348d05.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693480762929/90a8fb80-a753-4cec-b4b6-cde0f47597bd.avif
tags: linux, web-development, devops, jenkins, 90daysofdevops

---

## Introduction

In the ever-evolving landscape of software development, the principles of continuous integration and continuous delivery (CI/CD) stand as pillars of efficiency and quality. Enter Jenkins, the open-source automation server that's become synonymous with streamlined development pipelines. At its core lies the concept of agents, the unsung heroes that enable workload distribution and scalability. This article takes you on a journey into the heart of Jenkins agents, uncovering their roles, significance, and the art of setting them up for success.

## Jenkins Master: 🎮 The Command Center

Front and center in the Jenkins realm is the master node, often referred to as the Jenkins server. This powerful entity houses all the critical configurations and orchestrates the symphony of workflows within pipelines. It's the control tower that schedules jobs, keeps a watchful eye on their progress, and harmonizes the entire CI/CD landscape. With its vantage point, the Jenkins master ensures a seamless overview of the system and ensures tasks unfold seamlessly.

## Unveiling Jenkins Agents: 🕵️‍♂️

Beneath the surface of Jenkins lies a dynamic cast of agents. An agent, akin to a machine or container, establishes a connection with the Jenkins master and takes on the role of executing job-defined actions. Each time you create a Jenkins job, it's imperative to designate an agent. These agents are adorned with unique labels, acting as their distinct identifiers. Think of these labels as the guiding stars that direct Jenkins to match tasks with their designated agents.

Picture this: You trigger a Jenkins job from the master node. Instead of the master handling execution, the task is passed to the assigned agent node, following the job's specifications. This separation of roles—master for orchestration, and agents for execution—forms the bedrock of a scalable, efficient CI/CD framework.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692722833275/b8c4a7c0-9001-4e2e-a210-392b87a4c674.png?auto=compress,format&format=webp align="left")

## Master-Agent Synergy for Scaling: 🔄

While a single, monolithic Jenkins setup might suffice for small teams and projects, growth demands a different approach. Enter the "master to agent connection" paradigm. This innovative setup relieves a single system from the burden of both UI provisioning and job execution. By introducing multiple agents, the workload is judiciously distributed.

Here's the choreography: The Jenkins master takes the lead in UI provisioning and control. Simultaneously, agents, equipped with their unique capabilities and availability, execute assigned tasks. The result is a dance of parallelism, boosting responsiveness and efficiency within the CI/CD pipeline. This orchestrated partnership empowers Jenkins to adapt seamlessly to evolving development landscapes.

## Agent Integration: 🧩 Getting Started

Stepping into the realm of Jenkins agents requires adhering to a few prerequisites. Let's say you're beginning with a clean slate—installing Ubuntu 22.04 Linux. To set up an agent, follow these essential steps:

1. **Java Installation**: Harmony between the Java version on the agent machine and the Jenkins master server is crucial. Synchronization ensures smooth communication between these key players.
    
2. **Docker Adoption**: Docker provides an isolated, versatile environment for task execution. Equipping the agent machine with Docker ensures a consistent runtime environment.
    
3. **Rights and Permissions**: Attentive configuration of rights, permissions, and ownership for Jenkins users during agent setup is vital. This meticulous approach paves the way for unhindered agent functionality.
    

## **Step-by-Step Guide to Setting Up Jenkins Master-Slave Architecture with RSA Keys**

Jenkins, a powerful automation server, can significantly boost its performance by distributing build workloads across multiple machines using a master-slave setup. This step-by-step guide is tailored for beginners and aims to help you seamlessly establish a Jenkins master-slave architecture, complete with the use of RSA keys for secure authentication. Let's dive in!

**Step 1: Prepare Your Environment**

Before diving into the setup, ensure you have the following:

* A Jenkins master server (where the primary Jenkins instance is installed).
    
* A Jenkins slave server (the machine that will offload the build tasks from the master).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693479810051/bdbfd158-a02e-4bae-bf8c-2b9d47d71d29.png align="center")

**Step 2: Generate RSA Key Pair on Master Server**

1. Access the terminal on your Jenkins master server.
    
2. Navigate to the `.ssh` directory: `cd ~/.ssh`
    
3. Generate an RSA key pair: `ssh-keygen`
    
4. Follow the prompts to name the key pair (e.g., `id_rsa`) and set an optional passphrase. This passphrase adds an extra layer of security.
    
5. Verify the key generation: `ls`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693479985965/ad56eb1e-8569-4855-8815-7420f0038beb.png align="center")
    

**Step 3: Add Master Server's Public Key to Slave Server**

1. Retrieve the public key from the master server: `cat ~/.ssh/id_rsa.pub`
    
2. SSH into the slave server: `ssh <slave_username>@<slave_server_address>`
    
3. Navigate to the `.ssh` directory on the slave server: `cd ~/.ssh`
    
4. Open the `authorized_keys` file using a text editor: `nano authorized_keys`
    
5. Paste the master server's public key on a new line.
    
6. Save the changes and exit the text editor.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693479957650/562621bd-8124-4199-8b10-fb7ed5750882.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693479995128/880b2f7d-bbf0-42c1-b5f2-8ce7529925f9.png align="center")
    

**Step 4: Connect to Slave from Master Server**

1. In the terminal on the master server, use SSH to connect to the slave server: `ssh <slave_username>@<slave_server_address>`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693480023503/4502f5b0-8c81-4069-b4f0-7969774f07c8.png align="center")
    

**Step 5: Configure Slave Node on Jenkins**

1. Log in to your Jenkins instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693480044690/27201387-73ad-4687-a4f3-3efd68acd8dd.png align="center")
    
2. Go to "Manage Jenkins" &gt; "Manage Nodes and Clouds" &gt; "New Node".
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693480052247/317e3586-81cc-4ea9-b3b9-9fca499648d4.png align="center")
    
3. Provide a node name and select "Permanent Agent." Click "OK."
    
4. Configure the node settings:
    
    * Set the desired number of executors (build threads).
        
    * Define the remote root directory where Jenkins will work on the slave machine.
        
    * Assign labels for categorizing nodes.
        
    * Choose "Launch agent agents via SSH" as the launch method.
        
    * Enter the slave server's address as the host.
        
    * For credentials, choose "From the Jenkins master ~/.ssh" and select the private key associated with the public key added to the slave server.
        
5. Save the node configuration.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693480248418/f2abcb49-41c8-40bb-94d0-852742986cb7.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693480105633/1a8c91bd-805c-41ae-8eeb-77f7e2b6c7ce.png align="center")
    

**Step 6: Launch the Slave Agent**

1. In the "Nodes" list, locate your slave node and click on its name.
    
2. Click "Launch agent" to initiate the connection between the master and slave.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693480364936/2ee82fba-70bb-4ad9-89f7-eaf546bb008e.png align="center")
    

**Step 7: Create and Run a Pipeline**

1. Create a new pipeline job in Jenkins.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692726215080/500c4e5a-4cac-467a-979d-a4f4d21c759c.png?auto=compress,format&format=webp align="left")
    
2. Write the pipeline script to define the stages and steps of your build process.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692726218540/3180a951-8857-4007-b5d3-a7a262db99db.png?auto=compress,format&format=webp align="left")
    
3. Utilize the label assigned to the slave node to ensure the job runs on the slave machine.
    
4. Save the pipeline configuration and execute it.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692726228231/a224bcf0-a413-4640-9191-9f84e8d9d5b6.png?auto=compress,format&format=webp align="left")
    

**Conclusion: Optimized Build Distribution with Jenkins Master-Slave Architecture**

Congratulations! You've successfully set up a Jenkins master-slave architecture using RSA keys for secure authentication. This configuration distributes your build workload effectively, enhancing performance and resource utilization. As you explore more advanced features of Jenkins, this foundation will prove invaluable.

We hope this guide has been informative and beneficial. For more technology-related content and updates, stay connected by following me on and [LinkedIn](http://www.linkedin.com/in/adarsh2005). Happy building!