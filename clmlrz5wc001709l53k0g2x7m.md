---
title: "🚀📅 Day 42 DevOps Challenge - Streamline Your Builds with AWS CodeBuild 🚀 ☁"
datePublished: Sat Sep 16 2023 08:37:17 GMT+0000 (Coordinated Universal Time)
cuid: clmlrz5wc001709l53k0g2x7m
slug: day-42-devops-challenge-streamline-your-builds-with-aws-codebuild
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694853323322/9566b8c9-5455-4e34-86ff-50032b621a85.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694853401969/45099bd4-d8e8-446c-9712-00c859afc382.avif
tags: aws, devops, 2articles1week, 90daysofdevops, aws-codecommit

---

In the fast-paced world of software development, efficient and consistent build processes are essential for delivering high-quality applications. AWS CodeBuild, a fully managed build service in the cloud, simplifies and accelerates the build and test phase of your development lifecycle. Let's explore how CodeBuild can be a game-changer for your CI/CD pipeline.

## **Understanding AWS CodeBuild**

AWS CodeBuild is designed to compile your source code, run unit tests, and produce ready-to-deploy artifacts. It effectively removes the burden of provisioning, managing, and scaling your own build servers, allowing you to focus on writing and improving your code.

### **Key Advantages:**

1. **Managed Service** 🛠️: CodeBuild is a fully managed service provided by AWS. This means you don't have to worry about server provisioning, configuration, scaling, or maintenance.
    
2. **Customizable Build Environments** ⚙️: CodeBuild allows you to define custom build environments through build specifications. You can tailor these specifications to your project's specific requirements, including the build environment, build commands, and runtime versions.
    
3. **Scalability** 📈: CodeBuild automatically scales based on the size and needs of your build. It ensures optimal performance even during peak build times, handling your workload efficiently.
    
4. **Ease of Integration** 🤝: CodeBuild seamlessly integrates with other AWS services, making it a vital part of the AWS CI/CD ecosystem. It can pull source code from AWS CodeCommit, trigger builds based on commits and deploy artifacts to various AWS services.
    

## **Real-World Use Cases**

1. **Continuous Integration** 🔄: Automatically trigger builds on every commit to ensure that the codebase is continuously integrated and tested.
    
2. **Automated Testing** 🧪: Run comprehensive unit tests and integration tests as part of the build process to catch bugs early in the development cycle.
    
3. **Artifact Generation** 📦: Generate deployable artifacts, such as executable files, packages, or container images, as the output of the build process.
    
4. **Deployment** 🚀: Integrate CodeBuild with AWS CodeDeploy to automatically deploy your applications after a successful build.
    

### **Task-01: Set up a Basic HTML Page in CodeCommit 🏗️**

#### Step 1: Read about the Buildspec file for CodeBuild

* Before proceeding, make sure you have a good understanding of what a Buildspec file is and how it's used in AWS CodeBuild. Refer to the AWS CodeBuild documentation to familiarize yourself with the structure and syntax of a Buildspec file.
    

#### Step 2: Create a simple index.html file in CodeCommit Repository

1. Access or Create a new CodeCommit repository where you want to create the `index.html` file.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694850661733/d3050743-3630-43db-944e-63b190dcd139.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694850722504/948349d1-0404-4f91-bb7f-b9ef669625d0.png align="center")
    
2. Create a new file named `index.html` in the repository.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694850777128/bbeba069-0875-42c2-945c-6de7a2df9877.png align="center")
    
3. Add your HTML content to the `index.html` file. For example:
    
    ```bash
    <!DOCTYPE html>
    <html>
    <head>
        <title>My Simple Web Page</title>
    </head>
    <body>
        <h1>Hello, world!</h1>
    </body>
    </html>
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694850897249/16938701-651e-4d4b-b132-f85f450d98d3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694850938904/d0973a5b-c329-4671-a6c6-eb0a1eb11d56.png align="center")

#### Step 3: Build the index.html using nginx server

* To build the `index.html` using an nginx server, you'll need to set up a build process that uses an nginx Docker container or a similar approach. This can be defined in the `buildspec.yaml` file, which we'll cover in Task-02.
    

### **Task-02: Implement Build Automation with Nginx using CodeBuild 🛠️**

#### Step 1: Create a buildspec.yaml file

1. In the same CodeCommit repository, create a new file named `buildspec.yaml` .
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694851518094/c73116d5-b820-46df-80fa-4438312280a8.png align="center")
    

Open the `buildspec.yaml` file and define the build specifications. Here's a simple example:

```bash
version: 0.2

phases:
  install:
    commands:
      - echo "Installing Nginx"
      - sudo apt update
      - sudo apt install nginx -y   
  pre_build:
    commands:
      - echo "Starting the build..."
  build:
    commands:
      - echo "Building the index.html file using nginx..."
      - cp index.html /var/www/html/
  post_build:
    commands:
      - echo "Build completed successfully."
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694851630557/79e87c22-5b36-448e-892c-03ba2e4b8289.png align="center")

#### Step 2: Push the buildspec.yaml file to CodeCommit

* Save the `buildspec.yaml` file and commit it to the CodeCommit repository.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694851700377/07e1d5af-b5d1-4d5c-b558-232c1f7a3dc2.png align="center")
    

#### Step 3: Trigger the build in CodeBuild

* Create a CodeBuild project with a suitable name, select AWS CodeCommit as the source provider, choose the environment and build specifications (using a buildspec file), choose a service role, and optionally set additional project settings.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852039812/a9ee4ecd-2e19-4d83-bc36-da1b1e97c82c.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852122268/8403361b-ef0f-4d71-b416-9fe06afbb6cc.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852150896/2a4e74ff-2ffc-4cc1-a287-d31e37a12a1a.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852291049/30916a2a-e73f-43d8-a817-feccaedfcced.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852196582/ad86e666-1202-4f55-89af-ddfee7e9272b.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852343123/addc22b9-0f8a-4b8a-a984-dc80dca6fbdc.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852694523/7c6c0685-dccb-47f1-9e14-e2028dee4a83.png align="center")
    
    Now, when you click on "start build" CodeBuild will automatically build the `index.html` file using nginx as specified in the build process in the `buildspec.yaml` file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694852534195/28734add-912b-4b4e-87dd-24a96dc47097.png align="center")

**Note:-** In this project, we utilized the AWS Management Console exclusively and refrained from creating IAM users, roles, or attaching policies using the AWS CLI. All setup, including creating `index.html` and `buildspec.yaml`, as well as building the project was done via the console. This simplified approach highlights AWS services' accessibility without requiring command-line interactions.

## **Conclusion**

AWS CodeBuild provides a powerful and flexible solution for automating and scaling your build processes. By leveraging CodeBuild, you can streamline your development workflow, improve code quality, and accelerate your application delivery. Stay tuned for the next parts of this series as we explore more AWS services and how to integrate them into a robust CI/CD pipeline.

Happy building in the cloud! 🚀☁