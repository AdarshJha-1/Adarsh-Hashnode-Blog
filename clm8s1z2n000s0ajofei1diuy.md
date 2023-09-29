---
title: "🚀📅 Day 34 DevOps Challenge - IAM Programmatic Access and AWS CLI: Unlocking the Power of AWS from Your Terminal 🚀 ☁"
datePublished: Thu Sep 07 2023 06:18:28 GMT+0000 (Coordinated Universal Time)
cuid: clm8s1z2n000s0ajofei1diuy
slug: day-34-devops-challenge-iam-programmatic-access-and-aws-cli-unlocking-the-power-of-aws-from-your-terminal
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694064077391/da9860b8-08e4-43ed-a09c-b05d8cd34769.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694067413287/b130fe34-b38e-4f37-b26f-18d1fc1150c0.jpeg
tags: aws, web-development, cli, devops, 90daysofdevops

---

In today's fast-paced world of cloud computing, efficiency and automation are key. AWS (Amazon Web Services) has revolutionized the way organizations manage their cloud infrastructure, and one of the most powerful ways to harness this potential is through programmatic access using IAM (Identity and Access Management) and the AWS CLI (Command Line Interface). In this blog post, we'll delve into the world of IAM programmatic access and the AWS CLI, exploring how they empower AWS users to streamline their workflows, automate tasks, and unlock the full potential of AWS services.

# **IAM Programmatic Access: Your Key to AWS 🗝️**

### What is IAM Programmatic Access?🛠️ 📝 🎯

IAM Programmatic Access is a method that enables users to interact with AWS resources programmatically, rather than through the AWS Management Console. It involves using AWS Access Keys and AWS Secret Access Keys to authenticate requests made to AWS services, making it a secure and versatile way to access and manage your AWS account.

### Why Use IAM Programmatic Access?🤖 🔐

1. **Automation**: IAM Programmatic Access is the cornerstone of automating AWS tasks. By integrating AWS services into your scripts and applications, you can streamline workflows and reduce manual intervention.
    
2. **Fine-Grained Control**: IAM allows you to define precise permissions for users, ensuring that they only have access to the resources they need. This enhances security and minimizes the risk of unauthorized actions.
    
3. **Secure and Scalable**: Unlike hardcoding your AWS credentials, IAM Access Keys can be rotated regularly for enhanced security. This scalability feature is crucial in modern cloud environments.
    

# **AWS CLI: Your Command Center for AWS 💻**

![How to install the AWS Command Line Interface on MacOS – samirbehara](https://dotnetvibes.files.wordpress.com/2018/01/aws-cli.png?w=427&h=141 align="center")

### Introducing AWS CLI

The AWS Command Line Interface, or AWS CLI, is a versatile and powerful tool that allows you to manage your AWS services directly from your terminal. It's a unified interface for interacting with AWS services, providing a consistent and efficient way to control multiple AWS resources. With AWS CLI, you can perform a wide range of tasks, such as creating and configuring AWS resources, managing EC2 instances, and even deploying applications.

### Key Features of AWS CLI v2 🛠️ 🔄 📈

AWS CLI v2 comes with several exciting features that enhance its usability and functionality:

1. **Improved Installers**: Setting up AWS CLI v2 is now easier than ever, thanks to improved installers for various platforms. This ensures a seamless experience during installation and updates.
    
2. **Enhanced Configuration**: AWS CLI v2 introduces new configuration options, including integration with AWS IAM Identity Center, which is the successor to AWS SSO (Single Sign-On). This simplifies the management of AWS CLI configurations and credentials.
    
3. **Interactive Features**: AWS CLI v2 offers interactive prompts and autocompletion, making it more user-friendly and helping users discover available commands and options effortlessly.
    

By leveraging the AWS CLI v2, you can efficiently interact with AWS services, automate complex tasks, and integrate AWS into your development and operational workflows.

## **Task-01: Create AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY from AWS Console.**

1. **Log in to your AWS Management Console.**
    
    * Open your web browser and navigate to the **AWS** **Console**.
        
    * Sign in to your AWS account using your credentials.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694064550990/95a036b6-e79c-47f1-b06a-58971ab15dd5.png align="center")
        
2. **Access Your Security Credentials:**
    
    * After logging in, click on your username in the top right corner of the AWS Management Console.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694065084099/34b11a33-974a-4d42-b6e3-41cb94969496.png align="center")
        
3. **Select "Security Credentials" from the Drop-down Menu:**
    
    * In the drop-down menu that appears when you click your username, select "Security Credentials."
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694065110673/90017138-1e04-4cfa-ade0-9a09f26bfb0c.png align="center")
        
4. **Access the "Access keys (access key ID and secret access key)" Section:**
    
    * In the Security Credentials dashboard, locate the "Access keys (access key ID and secret access key)" section.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694065966318/84f16ad0-38a8-4c79-b948-249b75da0bd1.png align="center")
        
5. **Create an Access Key:**
    
    * Click on the "Create Access Key" button within this section.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694066143466/c67c2f32-2bfc-4a2c-ad79-381757384919.png align="center")
        
6. **View and Download Your Credentials:**
    
    * Your access key ID and secret access key will be displayed on the screen.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694066178823/4a4e4fdb-1836-4009-bda6-23fde880d9c8.png align="center")
        
    * Make sure to download the CSV file containing your access key information by clicking the "Download CSV" button.
        
    * Store this CSV file in a secure location, as it contains sensitive information necessary for accessing AWS services.
        

That's it! You have successfully created AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY from the AWS Console and securely stored them for your AWS account.

## **Task-02: Setup and Install AWS CLI and Configure Your Account Credentials on Ubuntu Linux**

1. **Install AWS CLI:**
    
    * Open a terminal on your Ubuntu Linux machine.
        
    * Update the package list to ensure you have the latest information on available packages:
        
        ```bash
        sudo apt update
        ```
        
    * Install the AWS CLI using the package manager:
        
        ```bash
        sudo apt install awscli
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694066917012/82077e10-c0d1-4277-8fdc-3c15f08c0db7.png align="center")
        
2. **Verify AWS CLI Installation:**
    
    * After installation, you can verify the AWS CLI installation by running the following command:
        
        ```bash
        aws --version
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694066952827/d793e99e-5101-455e-9266-4ceb0874a35b.png align="center")
        
    * You should see the installed AWS CLI version displayed in the output.
        
3. **Configure AWS CLI with Your Account Credentials:**
    
    * To configure the AWS CLI with your AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY obtained in Task-01, run the following command in your terminal:
        
        ```bash
        aws configure
        ```
        
    * You will be prompted to enter the following information:
        
        * AWS Access Key ID
            
        * AWS Secret Access Key
            
        * Default region name (e.g., us-east-1)
            
        * Default output format (e.g., JSON)
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694067069965/66917a1c-3b93-4b2a-a5b7-0d3641e36ffe.png align="center")
            
4. **Enter AWS Access Key ID and Secret Access Key:**
    
    * Enter the AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY from the CSV file you downloaded in Task-01 when prompted.
        
5. **Specify Default Region and Output Format:**
    
    * Set your preferred default region (e.g., us-east-1) and output format (e.g., JSON) as prompted. These settings can be modified later if needed.
        

You have now successfully set up and installed the AWS CLI and configured it with your AWS account credentials on Ubuntu Linux. You can use the AWS CLI to interact with AWS services from your terminal.

## **Conclusion 🎉**🙌 📚

IAM Programmatic Access and the AWS CLI are essential tools for AWS users seeking to maximize their productivity and efficiency. With IAM Programmatic Access, you can securely automate AWS tasks and manage permissions with precision. The AWS CLI, on the other hand, serves as your command center for AWS, simplifying interactions with various services and enabling you to harness the full potential of AWS.

In a world where agility and automation are paramount, mastering IAM Programmatic Access and the AWS CLI can be a game-changer for businesses and individuals alike. So, start exploring these tools today, and experience the power of AWS at your fingertips. Unlock the true potential of cloud computing and elevate your AWS experience to new heights. 🚀 ☁