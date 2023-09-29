---
title: "🚀📅 Day 39 DevOps Challenge - AWS Mastery: Test Knowledge on AWS"
datePublished: Tue Sep 12 2023 09:12:31 GMT+0000 (Coordinated Universal Time)
cuid: clmg3h2qh001h09l20tdj62c1
slug: day-39-devops-challenge-aws-mastery-test-knowledge-on-aws
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694510653089/37823a91-30a9-47bc-ac6f-1f9d5d382e8e.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694510662659/78481664-38bb-4792-838c-5ddb8c45f659.avif
tags: cloud, aws, web-development, devops, 90daysofdevops

---

Welcome to the "Test Knowledge on AWS" challenge as part of the 90 Days of DevOps Challenge! In this blog post, we will walk you through a series of tasks designed to test and expand your knowledge of Amazon Web Services (AWS). By the end of this exercise, you will have launched an EC2 instance, installed a web server, deployed a simple web application, and monitored the instance using Amazon CloudWatch.

## **Task: Launching an EC2 Instance, Setting Up a Web Server, and Monitoring with CloudWatch💻**

## Step 1: Launching an EC2 Instance 💻

The first step is to create an EC2 (Elastic Compute Cloud) instance using the AWS Management Console. EC2 instances are virtual servers in the cloud that you can configure and manage to run your applications.

1. **Log in to AWS Console**: Open your web browser and navigate to the **AWS** [](https://aws.amazon.com/)**Management** **Console**. Log in with your AWS credentials.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694504720149/57d85c20-ae7d-4990-b248-c7a9e227fb2c.png align="center")
    
2. **Access EC2 Dashboard**: Once logged in, go to the EC2 Dashboard by clicking on "Services" in the top left corner, then selecting "EC2" under the Compute section.
    
3. **Launch Instance**: Click the "Launch Instance" button to initiate the instance creation process.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694504772075/7a8cf6c0-8a62-4362-970e-7f528430b5ea.png align="center")
    
4. **Choose an Amazon Machine Image (AMI) 🖥️**: Select an AMI that suits your needs. For this example, choose a Linux AMI, like Amazon Linux 2 or Ubuntu.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694504805694/03484aa9-8825-4c68-9258-80c5f3ec472c.png align="center")
    
5. **Choose an Instance Type 💪**: Select an instance type based on your requirements. For beginners, a t2.micro instance should be sufficient.
    
6. **Key Pair**: Create a new key pair or use an existing one. You'll need this key pair to SSH into your instance. Download the private key file (.pem) and keep it secure.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694504851281/09dadd37-bebe-4a77-add6-16309b5448f9.png align="center")
    
7. **Configure Instance Details ⚙️**: Configure instance details such as the number of instances, network settings, and more. You can leave most settings at their defaults for this exercise.
    
8. **Configure Security Group 🔒**: Create or select a security group that allows SSH access (port 22) and HTTP access (port 80) to your instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694504923424/3db00962-d3f9-4447-b882-2dbb9cbf2a3d.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694504962583/e137a8b8-3aaa-49f1-874e-fabf8cc4720d.png align="center")
    
9. **Add Storage 📦**: Configure the storage settings for your instance. By default, AWS provides an 8 GB EBS (Elastic Block Store) volume.
    
10. **Review and Launch 🚀**: Review your instance configuration, then click "Launch Instances" to create your EC2 instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505017287/f29e1be0-44ac-46b0-b61b-1e028683e02d.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505081458/4151a015-e956-4efe-82b2-0987964526fc.png align="center")

## Step 2: Connecting to Your EC2 Instance 🌐

Now that you have an EC2 instance up and running, it's time to connect to it using SSH (Secure Shell).

1. **Open Terminal 🖥️**: If you're using Linux or macOS, open your terminal application. If you're on Windows, consider using an SSH client like PuTTY.
    
2. **Change Permissions 🔐**: Ensure that your private key (.pem) file is secure by running: `chmod 400 your-key.pem`
    
3. **SSH into Your Instance 🚪**: Use the following command to SSH into your instance, replacing `your-key.pem` and `your-instance-ip` with the actual file path and your instance's public IP address:
    
    ```bash
    ssh -i your-key.pem ec2-user@your-instance-ip
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505226428/2c4971a6-0ae5-45a6-82c5-75f3457b5d4c.png align="center")
    
4. You should now be connected to your EC2 instance via SSH.
    

## Step 3: Installing a Web Server and Deploying a Web Application 🌐

Now that you're connected to your EC2 instance, let's install a web server and deploy a simple web application. For this example, we'll use Apache as the web server and a basic HTML file.

1. **Update Packages 🔄**: Run the following command to ensure your system packages are up-to-date:
    
    ```bash
    sudo apt update -y
    ```
    
2. **Install Apache 🌐**: Install the Apache web server with:
    
    ```bash
    sudo apt install apache2 -y
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505371002/9e3fe546-0dd5-4eff-953f-80b8cc61e595.png align="center")
    
3. **Start Apache 🚀**: Start the Apache service:
    
    ```bash
    sudo service apache2 start
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505445322/d8ea1307-c7ae-4a7f-8cc3-5d678f9bc5a9.png align="center")
    
4. **Create a Simple Web Page 📄**: Create a basic HTML file to serve as your web application. You can use a text editor like `vi` or `nano`:
    
    ```bash
    echo "Hello, AWS DevOps Challenge!" | sudo tee /var/www/html/index.html
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505495324/c8ad460f-1364-4339-b26e-0f76f398d37e.png align="center")
    
5. **Access Your Web Application 🌐**: Open a web browser and enter your EC2 instance's public IP address. You should see your "Hello, AWS DevOps Challenge!" message.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505546646/5d8a945b-5790-4be1-a47f-47d3fcba833f.png align="center")
    

## Step 4: Monitoring with Amazon CloudWatch 📈

Amazon CloudWatch allows you to monitor various AWS resources, including EC2 instances. Let's set up some basic monitoring.

1. **Open CloudWatch Dashboard ☁️**: To begin, navigate to the AWS Management Console and select "Services." Under the "Management & Governance" section, click on "CloudWatch."
    
2. **Create an Alarm ⚠️**: In the CloudWatch dashboard, select "Alarms" from the left-hand navigation pane, and then click the "Create Alarm" button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694505985221/f0de87a7-d795-41ea-af0b-4153fb460608.png align="center")
    
3. **Select Metric 📊**: CloudWatch offers a wide range of metrics to monitor. For this example, let's set up an alarm based on CPU utilization. Click on "Select metric" to proceed.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506025317/03790b39-7972-4a54-b69c-857c2eafaaa5.png align="center")
    
4. **Choose a Metric 📈**: In the "Create Alarm" wizard, select "EC2" as the namespace, and then choose the specific instance and metric you want to monitor. In this case, select your EC2 instance and "Per-Instance Metrics" -&gt; "CPUUtilization." Click "Select metric."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506068810/6ac9402c-8f40-49ec-b9ca-f4c12d0da213.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506126884/118568e3-22cb-4fed-8a24-9b1f6a958b42.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506320642/71cb12dc-66bd-48d1-94f1-f4083e20846c.png align="center")
    
5. **Configure Conditions ⚙️**: Now, you'll need to configure the conditions that trigger the alarm. Set the conditions that make sense for your application. For instance, you might want to create an alarm if the CPU utilization exceeds 70% for a sustained period. Adjust the threshold and the evaluation period according to your requirements.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506403356/8e3b7086-0d4a-4a17-ba97-8fb1c334b5f5.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506435187/f07cbb83-99ca-4d55-95cc-1b6080c7eaed.png align="center")
    
6. **Configure Actions 📧**: Next, set up actions to be taken when the alarm state is triggered. This can include sending a notification email, triggering an AWS Lambda function, or performing Auto Scaling actions. Click on "Add notification."
    
    a. **Create SNS Topic 📢**: If you haven't already created an SNS topic, you'll be prompted to create one. An SNS topic acts as a communication channel to send notifications. Click on "Create topic."
    
    b. **Topic Details**: Provide a name and display name for your SNS topic. Then, click "Create topic."
    
    c. **Subscription**: Once the topic is created, you'll need to subscribe to it. Choose the protocol (e.g., email, SMS, or even an AWS Lambda function), and enter the recipient's information. For email subscriptions, you'll need to confirm the subscription by clicking on the link sent to your email address.
    
    d. **Back to Alarm Configuration**: After creating and subscribing to the SNS topic, you can now select it as the notification option in your CloudWatch alarm configuration.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506841888/0206c74d-d3e9-4ee8-a93d-f6fb42c80cef.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506900996/5894f80e-b4a4-40a3-abfd-842748df76c9.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694506984530/51b78831-480e-495d-a4a5-df2111d029b7.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694507145063/90735157-5295-4b90-9705-81556a764650.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694507176132/6c1be88a-0bba-4422-8855-a2d6c0711649.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694507195507/69bf44dc-e663-499c-a92a-2085173d7cfb.png align="center")
    
7. **Name and Describe Your Alarm 🚨**: Provide a name and description for your alarm to make it easy to identify its purpose.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694509733418/dbdd3c6c-0400-4b5b-a51c-dabf0b367c35.png align="center")
    
8. **Create Alarm 🚀**: Finally, review your alarm configuration to ensure it matches your requirements. Once you're satisfied, click the "Create alarm" button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694507786539/a8b30c99-9354-4cbe-8202-0b24d40c8895.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694509750233/8adc15d4-7e59-4960-a4e8-548698cada0c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694509760470/667c360f-6686-465e-a451-3328d3d1c7a2.png align="center")

Now you have a basic CloudWatch alarm set up to monitor your EC2 instance's CPU utilization. If it exceeds the defined threshold, you'll receive notifications.

## Conclusion 🎉

Congratulations! You've successfully completed the "Test Knowledge on AWS" challenge. You've launched an EC2 instance, connected to it via SSH, installed a web server, deployed a simple web application, and set up basic monitoring with Amazon CloudWatch. These fundamental AWS tasks are valuable building blocks for your journey into the world of DevOps and cloud computing. Keep exploring and experimenting to enhance your AWS skills further. 🚀