---
title: "🚀📅 Day 27 DevOps Challenge - Jenkins Declarative Pipeline with Docker Integration 🐳"
seoTitle: "day-27-devops-challenge-jenkins-declarative-pipeline-with-docker-integ"
seoDescription: "day-27-devops-challenge-jenkins-declarative-pipeline-with-docker-integration"
datePublished: Mon Aug 28 2023 03:41:49 GMT+0000 (Coordinated Universal Time)
cuid: clluc20ar000e09mldmq02o6h
slug: day-27-devops-challenge-jenkins-declarative-pipeline-with-docker-integration
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693194001803/c1b04816-f3de-4bde-b6e4-796b08001556.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693194088933/05945911-54ca-4bd0-810f-12e58a01ee74.png
tags: software-development, web-development, devops, 90daysofdevops, shubhamlondhe

---

## **Leveling Up Your Jenkins Pipeline with Docker 🛠️**

Welcome to another exciting installment of our Jenkins journey! 🌟 In our previous blog post, we dived deep into the world of Declarative pipelines and learned how to structure our CI/CD workflows using the power of declarative syntax.

## **The Docker Advantage ✨**

Before we dive into the nitty-gritty technical details, let's take a moment to understand why Docker is a game-changer for modern software development and deployment:

#### **Consistency Across Environments** ✔️

Docker containers ensure consistent runtime environments throughout various stages of your pipeline, from development to production. No more "it works on my machine" scenarios! 🙅‍♂️

#### **Enhanced Isolation 🏔️**

By encapsulating applications and their dependencies within containers, Docker minimizes conflicts between different applications and versions, making software deployment a breeze. 🚀

#### **Reproducible Environments 🔄**

With Docker, reproducing the exact same environment on different machines becomes effortless. This guarantees consistent behavior and reduces the chances of unforeseen issues cropping up. 🌐

#### **Efficiency and Resource Utilization 🚄**

Docker containers are lightweight compared to traditional virtual machines, resulting in faster deployment times, optimized resource utilization, and greater scalability. ⚙️

## **Seamlessly Integrating Docker into Jenkins Declarative Pipelines 🌐**

Let's roll up our sleeves and explore how we can seamlessly integrate Docker into our Jenkins pipeline using the intuitive declarative syntax. Our focus will be on two pivotal Docker commands: `docker build` and `docker run`. 💻

### **Defining the Stages 🛠️**

Within our Declarative Pipeline, we'll establish distinct stages for building and running our Docker container. Here's a peek at how these stages will shape up:

```bash
pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    sh 'docker build -t trainwithshubham/django-app:latest .'
                }
            }
        }
        
        stage('Run') {
            steps {
                script {
                    // Run the Docker container
                    sh 'docker run -d trainwithshubham/django-app:latest'
                }
            }
        }
    }
}
```

#### **Build Stage 🏗️**

In the "Build" stage, we leverage the `docker build` command to assemble a Docker image. The `-t` flag helps us tag the image for easy reference, while the `.` denotes the build context – the directory housing the Dockerfile and any requisite resources. 🛠️

#### Run Stage 🏃‍♂️

Transitioning to the "Run" stage, we initiate a container using the image crafted in the prior stage. The `-d` flag launches the container in detached mode, freeing up the terminal. We identify the image by its tag, such as `trainwithshubham/django-app:latest`. 🚀

## **Task-01: Create a Docker-Integrated Jenkins Declarative Pipeline 🐳**

Follow these steps to create a Jenkins declarative pipeline that integrates Docker using the provided syntax:

1. Open your Jenkins instance and navigate to the Jenkins dashboard.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693192039457/3ab3caa5-d808-47d1-817d-60edb389021e.png align="center")
    
3. Click on "New Item" to create a new Jenkins pipeline job.
    
4. Provide a name for your pipeline job and select "Pipeline" as the project type.
    
5. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693192126793/42020f69-ce0a-4e9e-85da-5cda9937bf7e.png align="center")
    
6. Scroll down to the "Pipeline" section and choose "Pipeline script" from the Definition dropdown.
    
7. Now, let's use the provided syntax inside the `script` block of the pipeline:
    
8. ```bash
    pipeline {
        agent any
        stages {
            stage('Code Clone') {
                steps {
                    git url: 'https://github.com/AdarshJha-1/node-todo-cicd.git', branch: 'master'
                }
            }
            stage('Build') {
                steps {
                    sh 'docker build -t node-todo-cicd:latest .'
                }
            }
            stage('Testing') {
                steps {
                    echo 'Testing'
                    // You can add actual testing steps here
                }
            }
            stage('Deploy') {
                steps {
                    sh 'docker run -d -p 8000:8000 node-todo-cicd:latest'
                }
            }
        }
    }
    ```
    
9. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693192209628/4cdea2e5-0308-4177-8ba0-4be27dc0cfcc.png align="center")
    
10. Click on the "Save" button to save your pipeline configuration.
    
11. Run the pipeline job by clicking on the "Build Now" button.
    
12. The pipeline will execute the build and run stages, creating a Docker container with your application.
    
13. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693192571816/cfdbf63b-f64f-4d86-bf0e-38d37c9c1216.png align="center")
    
14. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693192589252/8ab15d8e-004e-4bd7-8e69-2d989ab68cd0.png align="center")
    

**Since running the job twice might result in errors due to the Docker container already being created**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693193612012/2c520f34-f8c9-493b-a3e9-b7a032fab5f3.png align="center")

**you can implement a solution to address this issue. Here's how you can do it:**

## **Task-02: Docker-Integrated Jenkins Declarative Pipeline with Docker Compose Approach 🐳**

In Task-01, we successfully created a Docker-integrated Jenkins declarative pipeline to build, test, and deploy our application. However, when rebuilding the project, a common issue emerges due to the previously built container still occupying the same port, leading to conflicts. To address this using a Docker Compose approach without modifying the Docker Compose file, follow the steps below:

### **Solution:**

1. **Modify Jenkins Declarative Pipeline:**
    
    * Open your Jenkins pipeline job and navigate to the pipeline script section.
        
    * Update the "Deploy" stage to use Docker Compose commands for managing containers:
        
    
    ```bash
    pipeline {
        agent any
        stages {
            stage('Code Clone') {
                steps {
                    git url: 'https://github.com/AdarshJha-1/node-todo-cicd.git', branch: 'master'
                }
            }
            stage('Build') {
                steps {
                    sh 'docker build -t node-todo-cicd:latest .'
                }
            }
            stage('Testing') {
                steps {
                    echo 'Testing'
                    // You can add actual testing steps here
                }
            }
            stage('Deploy') {
                steps {
                    sh 'docker-compose down' # Stop and remove existing containers
                    sh 'docker-compose up -d' # Start new containers
                }
            }
        }
    }
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693193658687/ff8a235f-d05c-4c19-ba0a-1a1cf753838a.png align="center")
    
2. **Save and Rebuild:**
    
    * Click on the "Save" button to save your pipeline configuration.
        
    * Run the pipeline job by clicking on the "Build Now" button.
        
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693193698231/c29e6fd9-bc0a-440c-aa8d-3f0a8364dc19.png align="center")
        

**How it Works:**

By employing Docker Compose's `docker-compose down` and `docker-compose up` commands within the pipeline, we ensure that existing containers are stopped and removed before launching new containers. This approach guarantees that the previously running container on the same port will be stopped, and the new container will take its place on the same port, preventing conflicts.

With these adjustments, you can confidently rebuild the project without encountering port-related errors caused by running containers on the same port.

Follow these steps to enhance your build and deployment workflow, ensuring that your containers operate smoothly without conflicts

### **Conclusion 🎉**

Incorporating Docker into Jenkins pipelines has revolutionized software deployment! 🐳🚀 Achieving consistent environments, streamlined isolation, and efficient resource utilization, Docker offers a game-changing advantage. The synergy between Docker's capabilities and Jenkins' declarative pipelines empowers seamless integration through "docker build" and "docker run" commands. Tackling port conflicts, Docker Compose ensures smooth deployments. Keep exploring Docker's vast potential for networking and orchestration. With this newfound expertise, you're primed to conquer the dynamic landscape of CI/CD. Happy coding! 💻🎉