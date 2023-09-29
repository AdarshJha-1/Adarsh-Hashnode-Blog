---
title: "🚀📅 Day 43 DevOps Challenge - Your AWS CI/CD Journey: Unveiling CodeDeploy 🚀 ☁"
datePublished: Sun Sep 17 2023 09:13:21 GMT+0000 (Coordinated Universal Time)
cuid: clmn8pel8000808mo495d1nqc
slug: day-43-devops-challenge-your-aws-cicd-journey-unveiling-codedeploy
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694941945478/c6e3f4a9-dd20-4056-9287-de17c3464bdb.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694941994531/5984538b-dd76-46e3-882c-f1e5b88ee95f.avif
tags: aws, web-development, devops, codenewbies, 90daysofdevops

---

Welcome back to the third installment of our series on creating a seamless CI/CD pipeline on AWS. In the previous parts, we covered setting up AWS CodeCommit and CodeBuild to manage your source code and build artifacts. Today, we're diving into the next set of tools and services vital for a robust CI/CD workflow: CodeDeploy, CodePipeline, and S3. 🚀

## **What is CodeDeploy? ☁**

AWS CodeDeploy is a pivotal deployment service offered by Amazon Web Services that streamlines the process of application deployments. It allows for automated deployments to various targets such as Amazon EC2 instances, on-premises servers, serverless Lambda functions, or Amazon ECS services.

CodeDeploy facilitates the deployment of application content stored in Amazon S3 buckets, GitHub repositories, or Bitbucket repositories. Furthermore, it supports the deployment of serverless Lambda functions, making it versatile and adaptable to different application architectures. The best part? You don't need to modify your existing code to integrate CodeDeploy into your deployment process. 🌐

Now, let's explore how CodeDeploy can enhance your CI/CD pipeline. 🚀

## **Streamlining Deployment with CodeDeploy 🔄**

AWS CodeDeploy offers several advantages when integrated into your CI/CD pipeline:

### **1\. Automated Deployments 🤖**

CodeDeploy automates the deployment process, saving you time and reducing the possibility of human error. Once your build is ready, CodeDeploy takes over and ensures a smooth deployment to your specified targets.

### **2\. Easy Rollbacks ↩️**

In case of any issues with a deployment, CodeDeploy allows for seamless rollback to a previous, stable version. This ensures that you can quickly revert to a working state if any problems arise during deployment.

### **3\. Deployment Configurations 🛠️**

CodeDeploy lets you define various deployment configurations, enabling you to customize deployment strategies according to your application's needs. Whether it's a blue-green deployment, in-place deployment, or a canary release, CodeDeploy provides the flexibility to choose the right strategy for your scenario.

### **4\. Integration with Multiple Sources 🔄**

CodeDeploy supports various sources for application content, including Amazon S3, GitHub, and Bitbucket. This flexibility allows you to maintain your code in a repository of your choice and deploy directly from there.

# **Task-01 :**

### Deploy index.html file on EC2 machine using nginx

* For code commit and code build steps, please follow Day 42 task article.
    

### Create a CodeDeploy application

* In AWS Management Console search CodeDeploy. Once you are into the CodeDeploy go to Applications which is inside Deploy and click on 'Create application'.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685854486419/2099fa85-11ac-4a48-ac9d-6b6ef8363d59.png?auto=compress,format&format=webp align="left")
    
* Select compute platform 'EC2/on premises' and click on 'Create application'.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685854544787/2850caae-8aeb-4cfc-a57b-eb662cb27ab6.png?auto=compress,format&format=webp align="left")
    
* The application is successfully created.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685854588210/ea8e98a6-b34f-4e4b-a755-c1756e1292f5.png?auto=compress,format&format=webp align="left")
    
* Create a new service role for enabling communication between code deploy and other AWS services.
    
    Go to IAM service and create 'code-deploy-service-role' with permissions.
    
    "AmazoneEC2FullAccess", "AmazoneS3FullAccess", "AWSCodeDeployRole", "AmazoneEC2RoleforAWSCodeDeploy", "AWSCodeDeployFullAccess", "AmazonEC2RoleforAWSCodeDeployLimited".
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694938738561/f9133066-2062-4d3a-83dd-bd505355f991.png align="center")
    
    * Change the Trust Relationship
        
        ```bash
          {
              "Version": "2012-10-17",
              "Statement": [
                  {
                      "Effect": "Allow",
                      "Principal": {
                          "Service": [
                              "codedeploy.amazonaws.com"
                          ]
                      },
                      "Action": "sts:AssumeRole"
                  }
              ]
          }
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685857015653/3e03056a-ffa6-415b-bcf3-12dbd61cc613.png?auto=compress,format&format=webp align="left")
        
    
    ### Set up an EC2 instance
    
    * You will need to create an EC2 instance on which you want to deploy the **index.html** file.
        
        Create a Ubuntu EC2 instance
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856283715/61a269a2-4bd9-4889-8229-5f24776a6a43.png?auto=compress,format&format=webp align="left")
        
    
    ### Create a deployment group
    
    * Once you have created a CodeDeploy application, you need to create a deployment group. A deployment group is a set of EC2 instances where you want to deploy your application.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856327482/1928c683-8073-4757-bff1-f68905cd9640.png?auto=compress,format&format=webp align="left")
        
    * Add a deployment group name and choose the Service role where we provide all the permission policies.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694939006769/5ee7a726-e0c5-429e-b252-1b066241f641.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856445700/fb7d2c0d-3d50-4d4f-8578-43b58ceee772.png?auto=compress,format&format=webp align="left")
        
    * Provide the EC2 instance name that was created before.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856550480/30df22e8-6a79-4a22-9f67-078658f61ad7.png?auto=compress,format&format=webp align="left")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856619342/866fe2ea-93e0-4dde-85f2-d3c2bc5b7bce.png?auto=compress,format&format=webp align="left")
        
    * Click on 'Create deployment group'.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856642507/919d549f-36c9-4bd4-9e49-ea93b41b2e66.png?auto=compress,format&format=webp align="left")
        
    * A deployment group is created.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685856974290/1d3d6625-5a8c-4dfb-abbb-5edc84e267b8.png?auto=compress,format&format=webp align="left")
        
    
    ### Setup a CodeDeploy agent to deploy code on EC2
    
    * **Install the CodeDeploy agent:**
        
        You need to install the CodeDeploy agent on your Ubuntu EC2 instance. The CodeDeploy agent is a software package that runs on your instance and interacts with CodeDeploy to deploy your application.
        
    * You can install the CodeDeploy agent by running the following script on your EC2 instance:
        
        ```bash
            #!/bin/bash 
            # This installs the CodeDeploy agent and its prerequisites on Ubuntu 22.04.  
            sudo apt-get update 
            sudo apt-get install ruby-full ruby-webrick wget -y 
            cd /tmp 
            wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/releases/codedeploy-agent_1.3.2-1902_all.deb 
            mkdir codedeploy-agent_1.3.2-1902_ubuntu22 
            dpkg-deb -R codedeploy-agent_1.3.2-1902_all.deb codedeploy-agent_1.3.2-1902_ubuntu22 
            sed 's/Depends:.*/Depends:ruby3.0/' -i ./codedeploy-agent_1.3.2-1902_ubuntu22/DEBIAN/control 
            dpkg-deb -b codedeploy-agent_1.3.2-1902_ubuntu22/ 
            sudo dpkg -i codedeploy-agent_1.3.2-1902_ubuntu22.deb 
            systemctl list-units --type=service | grep codedeploy 
            sudo service codedeploy-agent status
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694939075657/fa2b8ed9-9877-440b-8b50-acf61242542b.png align="center")
        
    * Run the script using bash command.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694939102723/7a3c8041-5303-48bb-a2b4-888611caee73.png align="center")
        
    * We can verify the status that Code Agent is running.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685857245102/206563a2-40ba-4291-8fa7-03895e627770.png?auto=compress,format&format=webp align="left")
        
    * Create an index.html file:
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694939449041/0577f538-8df7-4724-b700-4a8539a3f33a.png align="center")
        
    
    ---
    
    # Task-02 :
    
    ### **Create an appspec.yaml file:**
    
    * You need to create an appspec.yaml file that tells CodeDeploy what to do with your application.
        
    * Here is an appspec.yaml file that deploys the index.html file on nginx. also, create 2 scripts for installing nginx and starting nginx.
        
    
    ```bash
        version: 0.0
        os: linux
        files:
          - source: /
            destination: /var/www/html
        hooks:
          AfterInstall:
            - location: scripts/install_nginx.sh
              timeout: 300
              runas: root
          ApplicationStart:
            - location: scripts/start_nginx.sh
              timeout: 300
              runas: root
    ```
    
    * Create start\_[**nginx.sh**](http://nginx.sh/) in the scripts folder
        
    
    ```bash
    #!/bin/bash
    
    sudo service nginx start
    ```
    
    * Create install\_[**nginx.sh**](http://nginx.sh/) in the scripts folder
        
    
    ```bash
    #!/bin/bash
    
    sudo apt-get update
    sudo apt-get install nginx -y
    ```
    
    * Push all the files to code commit using 'git add' and 'git commit' commands.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685858050273/43e44e5b-c8c6-43bd-be17-088fe4d17b2e.png?auto=compress,format&format=webp align="left")
        
    * All the files are updated in the CodeCommit.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685863946880/939322c7-b41b-474c-9bac-a7c072bd3f14.png?auto=compress,format&format=webp align="left")
        
    * Add changes to the buildspec.yml file
        
        ```bash
          version: 0.2
        
          phases:
            install:
              commands:
                - echo Installing NGINX
                - sudo apt-get update
                - sudo apt-get install nginx -y
            build:
              commands:
                - echo Build started on 'date'
                - cp index.html /var/www/html/
            post_build:
              commands:
                - echo Configuring NGINX
        
          artifacts:
              files:
                - '**/*'
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685863994906/41091cd4-ece9-4e32-9e8d-9b08dee806ac.png?auto=compress,format&format=webp align="left")
        
    * In build projects, Edit and choose 'Artifacts'.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685858252101/cf7eba7c-7ce4-431b-b136-48cbc208f0ac.png?auto=compress,format&format=webp align="left")
        
    * Create a new S3 bucket.
        
    * In Artifacts, select artifact type as Amazon S3 and choose bucket name.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694940239071/94d22881-559f-4085-9cb3-16ac2565e1a4.png align="center")
        
    * Click on 'Update artifacts'.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685858707221/8d9e90a2-859d-484a-84ce-c4561a4f1cc3.png?auto=compress,format&format=webp align="left")
        
    * Artifact upload location successfully added. Click on 'Start build'.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694940576735/2c65358f-58f5-4489-872b-32f75ddc275e.png align="center")
        
    * The build is Succeeded.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685859871615/e3b640e0-e5a6-49be-b206-6c2c9a62335f.png?auto=compress,format&format=webp align="left")
        
    * After building completion, go to the S3 bucket and copy the S3 URL of the nginx\_app-dep zip file.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694940781150/70f4d9ec-387e-4c82-a697-dea93a6ed5d8.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694940826057/79242334-df15-469d-aba9-4af6f9522b00.png align="center")
        
    
    ### **Create deployment:**
    
    * In the Application, Go to Deployments and click on 'Create deployment'
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685860094641/d9a1dd05-e95c-4915-bd79-40974ef19b11.png?auto=compress,format&format=webp align="left")
        
    * In revision type, select Amazon S3 and paste the above copied S3 url to the revision location
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694941138729/1b344e3c-555b-4cb4-8fa9-eac52b55b197.png align="center")
        
    * Click on 'Create deployment'.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685860300134/2a749836-a541-4ac3-a1fc-fcfccee5b684.png?auto=compress,format&format=webp align="left")
        
    * Deployment is created. but events are in a pending state.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685860333011/3357f034-ffe3-46cf-b76f-bf91e0afa539.png?auto=compress,format&format=webp align="left")
        
    * EC2 doesn't have any role policy to retrieve the data from S3 to CodeDeploy.
        
        To create a new service role for enabling communication between EC2 and S3, code deploy.
        
        * Go to IAM service and create 'EC2-S3-CodeDeploy' with permissions.
            
            "AmazoneEC2FullAccess", "AmazoneS3FullAccess", "AWSCodeDeployFullAccess".
            
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694941192324/a3a997b4-d925-419e-b8f8-e53050447fab.png align="center")
        
    * Attach that service role to the EC2 instance.
        
        Select EC2 instance, In actions, go to security and click on 'Modify IAM role'.
        
        Select the service role that we created in the above steps.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685860498679/2a284133-f8c3-4dbb-8f96-1b5c553bf425.png?auto=compress,format&format=webp align="left")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685860513434/f7bc4292-78f9-4aae-a7ec-12e1671cc1a1.png?auto=compress,format&format=webp align="left")
        
    * After updating the IAM role, restart the code-deploy agent.
        
        ```bash
          sudo service codedeploy-agent restart
          sudo service codedeploy-agent status
        ```
        
    * Deployment status is Succeeded.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685864438373/4d7edb4e-669e-41a4-8eb9-3430b39e8b97.png?auto=compress,format&format=webp align="left")
        
    * All events Succeeded.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694941872548/91f85be8-512c-45e4-9ef1-7fbf0eadfad5.png align="center")
        
    * Browse the instance public IP address, it will show the output of the index.html file.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685864552897/2f817725-c94b-41cc-9ad8-696fa213b640.png?auto=compress,format&format=webp align="left")
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694941526445/28cb43fc-ba1e-49de-9296-a127fc4ae7eb.png align="center")

Stay tuned for our next blog post, where we'll explore CodePipeline and its integration into your CI/CD workflow. We're excited to guide you through this journey to master CI/CD on AWS! 🌟

Keep innovating, keep deploying, and embrace the power of AWS! 🚀 ☁