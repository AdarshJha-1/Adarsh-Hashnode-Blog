---
title: "🚀📅 Day 30 DevOps Challenge - Getting Started with AWS Basics ☁"
datePublished: Sun Sep 03 2023 09:06:14 GMT+0000 (Coordinated Universal Time)
cuid: clm38abgx000309l55a0be8tr
slug: day-30-devops-challenge-getting-started-with-aws-basics
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693731443408/f7b52114-a7fa-4237-9d65-b7006525c5d6.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693731898484/33afb1c4-074f-4fe1-b222-cd3ccbff650c.png
tags: aws, automation, devops, iam, 90daysofdevops

---

## **Introduction 🚀**

Congratulations on taking the first step towards your cloud journey! In today's tech-driven world, cloud computing has become an indispensable part of businesses and individuals alike. Think of the cloud as a magical place where you can store your data, run applications, and perform all sorts of digital wizardry. Amazon Web Services (AWS) is like your magic wand in this realm, offering a plethora of services and resources to make your cloud dreams come true. Whether you're a student or a cloud enthusiast, AWS even provides a free tier for hands-on learning, making it the ideal platform to begin your cloud adventure. So, let's embark on this enchanting journey together!

![Top 50+ AWS Services Explained in 10 Minutes - YouTube](https://i.ytimg.com/vi/JIbIYCM48to/maxresdefault.jpg align="left")

## **Chapter 1: Understanding AWS ☁**

Imagine AWS as a gigantic digital mall where we can rent spaces and services to set up our shops or businesses. This mall spans the globe, with branches (data centers) in various cities. It's like having a store in every major city worldwide, which helps our customers to access our products quickly, no matter where they are. Whether we are selling shoes or streaming videos, AWS has a shop for it.

But here's the magical part: we can expand your shop to cover the entire mall or shrink it down to a tiny kiosk, depending on how many customers we have. This scalability, reliability, and global reach make AWS stand out in the cloud realm.

## **Chapter 2: Setting Up Your AWS Account 🏦**

Before we can start exploring the magical mall of AWS, you need to create an AWS account. Luckily, AWS offers a free tier, which is like having a free pass to the mall for your first 12 months. To get your pass:

1. Visit the AWS website ([**https://aws.amazon.com/**](https://aws.amazon.com/)).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693724335208/43120c26-a699-4e57-8c17-e417f209e999.png align="center")
    
2. Click on the "Complete Sign up" button.
    
3. Click on the "Create an AWS Account" button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693724456070/a9cd3a30-9d00-43aa-9d41-739cf2db3457.png align="center")
    
4. Follow the on-screen instructions to provide your information and set up your account.
    

Once we have our account, we'll receive a shiny AWS Management Console key that opens the doors to the mall. Now, we can start exploring and using AWS services like a seasoned mall-goer.

## **Chapter 3: AWS Identity and Access Management (IAM) 🔐**

### IAM - Identity and Access Management

🔐 IAM, which stands for Identity and Access Management, is a crucial service provided by Amazon Web Services (AWS) that allows us to manage user identities and control their access to AWS resources. Think of IAM as the gatekeeper to our AWS kingdom. It ensures that only the right individuals or systems can access our AWS resources and that they can only perform authorized actions.

![AWS — IAM Overview. What is AWS Identity and Access… | by Ashish Patel |  Awesome Cloud | Medium](https://miro.medium.com/v2/resize:fit:1400/1*CgfJAcRlay0O9amULak-fw.png align="left")

**Key Components of IAM:**

👤 **User Identities:** In AWS, a user can be a real person or an application that needs to interact with AWS services. IAM allows you to create and manage these user identities. Each user gets a unique set of credentials (username and password or access keys) to access AWS resources.

👥 **Groups:** Instead of managing permissions for each user individually, we can organize users into groups based on their roles or responsibilities. For example, we can have an "Admins" group, a "Developers" group, and so on. Then, we assign permissions to these groups collectively, making it easier to control access.

**👑 Roles:** IAM also supports roles, which are similar to users or groups but are typically used by services or applications rather than individuals. For example, we can create a role that allows an EC2 instance to access specific S3 buckets without having to store any credentials on the instance itself.

📜 **Permissions and Policies:** Permissions in IAM are defined using policies. Policies are like rulebooks that specify what actions are allowed or denied on which AWS resources. These policies can be attached to users, groups, or roles. AWS provides a set of predefined policies, but we can also create custom policies tailored to your needs.

🔒 **Access Control Lists (ACLs):** IAM enables you to set fine-grained permissions, controlling access to specific AWS services and resources. For example, we can grant a user read-only access to an S3 bucket, allowing them to view but not modify the contents.

**🔑 Multi-Factor Authentication (MFA):** For an added layer of security, IAM supports multi-factor authentication. Users can be required to provide a secondary authentication method, such as a time-based one-time password (TOTP) or a hardware token, in addition to their regular password.

**📋 Audit Trail:** IAM maintains detailed logs that record all actions taken by users and roles within your AWS account. These logs can be invaluable for security auditing and troubleshooting.

*In summary, IAM is a comprehensive access management system that helps us secure our AWS resources by controlling who can access them and what actions they can perform. It allows us to set up a secure and organized structure for managing user identities and permissions within your AWS environment, contributing to the overall security and compliance of your AWS resources and applications. 🔒🌐💼*

## **Task 1: IAM User Setup, EC2 Access, and Shell Script for Jenkins and Docker Installation**

**Step 1: Create an IAM User**

1. **Sign in to your AWS Management Console**: Go to the AWS Console ([**https://aws.amazon.com/**](https://aws.amazon.com/)) and sign in with your AWS account.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693726975665/50cbc803-1087-4985-bb8b-eecf35319485.png align="center")
    
2. **Access the IAM Dashboard**: Navigate to the Identity and Access Management (IAM) service from the AWS Console.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727034450/9c33c675-9c9a-4d7b-96db-471db2bc090d.png align="center")
    
3. **Create a New IAM User**:
    
    * Click on "Users" in the left navigation pane.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727178579/7e83c572-3149-4400-826a-522653a31575.png align="center")
        
    * Click the "Add user" button.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727209481/6d1f8364-f2f1-4982-9fac-f3ab11351522.png align="center")
        
4. **User Details**:
    
    * Enter a desired username for your IAM user.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727460391/1296165a-8d44-4591-8c3d-e16bfb4b3e88.png align="center")
        
    * Click "Next: Permissions."
        
5. **Attach Permissions**:
    
    * In the "Set permissions" step, click "Attach policies directly" to attach policies.
        
    * Search for and select the policy named "AmazonEC2FullAccess." This policy grants full access to EC2 resources.
        
    * Click "Next: Tags" (you can skip adding tags for this example).
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727605069/98f80968-5bbc-4175-9e19-e63f72b25cd6.png align="center")
        
    * Click "Next: Review."
        
6. **Review**:
    
    * Review the user's details and attached policies.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727743415/d3b222c5-9ad1-4d81-9623-afda9b7fe117.png align="center")
        
    * Click "Create user."
        
7. **Success**:
    
    * You'll see a confirmation that the user has been created.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693727783406/3263c3b9-e216-49a2-b76f-f4d81362bb44.png align="center")
        
    * **IMPORTANT**: Download the CSV file that contains the access key ID and secret access key. You'll need these credentials to configure your AWS CLI.
        

**Step 2: Launch a Linux EC2 Instance**

Now that we have an IAM user with EC2 access, you can use the AWS Management Console to launch an EC2 instance:

1. Sign in to the AWS Management Console if you're not already logged in.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728005412/3ae64710-0c56-477d-b7ec-f3877b24a4ec.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728140666/45c1f52e-d78f-41d2-9c3a-53cd45fdb68c.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728150103/2f2bbd3b-99d2-40af-99bc-5cbf5170fbac.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728181624/b42eec17-b977-4204-b2dc-11668e15cc23.png align="center")
    
2. Go to the EC2 dashboard.
    
3. Click the "Launch Instance" button to start the EC2 instance creation process.
    
4. Follow the EC2 instance creation wizard, specifying instance details, adding storage, configuring security groups (ensure that SSH access is allowed for connecting to your instance), and finally, reviewing and launching the instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728261957/f85c8e51-3fec-498e-a6d7-5292bd21490c.png align="center")
    

**Step 3: Install Jenkins and Docker with a Shell Script**

Once your EC2 instance is up and running, you can SSH into it and execute a shell script to install Jenkins and Docker.

Here's a sample shell script ([`install-jenkins-docker.sh`](http://install-jenkins-docker.sh)) that you can use:

```bash
#!/bin/bash

# Update the system
sudo apt update -y

# Install Java
sudo apt install openjdk-17-jre

# Install Jenkins
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

# Start Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins

# Install Docker
sudo apt install docker.io -y
sudo service docker start
sudo usermod -aG docker
```

1. SSH into your EC2 instance using the key pair you specified when launching it.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728373039/8c639dd6-3ec4-4242-aa0a-622f0fc43ecd.png align="center")
    
2. Create one [`install-jenkins-docker.sh`](http://install-jenkins-docker.sh) script on your instance using `vim` or `nano`any method you prefer.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728841811/5d2af145-c2ce-4528-a9b9-9d0a474ca0cf.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728876424/93160629-5801-4f11-afab-e6fa4cd3ce3e.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693728936194/2f343eef-a786-4cf2-94cc-6a10e1d16543.png align="center")
    
3. Run the script:
    

```bash
chmod +x install-jenkins-docker.sh
./install-jenkins-docker.sh
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693729083440/1503d38d-5ce0-45dc-94f9-bbe8f1aca0dd.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693729138396/463398eb-00ff-4752-ab19-e8500c586fae.png align="center")

This script will update the system, install Jenkins, install Docker, and configure them to start on boot.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693729268827/ed85f08e-650d-431c-ab86-18fb156e52a6.png align="center")

Once the script completes, Jenkins and Docker should be installed and running on your EC2 instance. You can access Jenkins via the EC2 instance's public IP address on port 8080 ([http://YOUR\_EC2\_PUBLIC\_IP:8080](http://YOUR_EC2_PUBLIC_IP:8080)) and configure it as needed.

## **Task 2: Building the DevOps Avengers Team and IAM User Management**

Creating a DevOps team of "Avengers" involves setting up IAM (Identity and Access Management) users, creating a DevOps group, and assigning IAM policies to the group. Below are the steps to accomplish this task using AWS as an example:

**Step 1: Create IAM Users**

1. Sign in to your AWS Management Console.
    
2. Go to the IAM dashboard.
    
3. Click on "Users" from the left-hand navigation pane.
    
4. Click "Add user."
    
    *( Repeat the previously mentioned steps exactly as described. )*
    
5. Enter a username for the first Avengers DevOps team member (e.g., avenger1).
    
6. Set a custom password or let AWS generate one for you. Make sure to save or securely share this password with the user.
    
7. Optionally, you can force the user to reset their password on their first login.
    
8. Click "Next: Permissions."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693730458976/c71eca46-3ac0-41e3-900d-433e1f7c7049.png align="center")
    

**Step 2: Create an IAM Group**

1. Click "Add group."
    
2. Enter a name for the group, like "DevOpsAvengers."
    

**Step 3: Assign Permissions to the Group**

1. In the "Attach permissions policies" section, search for the policies you want to assign to the DevOps team. You may need to create custom policies specific to your DevOps requirements.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693730598742/aa7cb68d-dd1d-424d-a5e7-323cf9e03af0.png align="center")
    
2. Select the desired policies. For a typical DevOps team, policies related to EC2, S3, RDS, CodeDeploy, CodePipeline, and other relevant services should be considered.
    
3. Review the group settings and policies, and click "Create group."
    

**Step 4: Add IAM Users to the DevOps Group**

1. After creating the "DevOpsAvengers" group, you'll be prompted to add users to the group. Select the IAM users we created earlier (e.g., avenger1), and click "Add users to group."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693730679211/780a2054-71bb-4b05-a805-0cea4cb84290.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693730712136/42ae5254-7be5-4493-855d-cdacb66bab29.png align="center")

**Step 5: Repeat for Other Avengers**

Repeat Steps 1-4 for the other two Avengers DevOps team members (e.g., avenger2 and avenger3), assigning them to the same "DevOpsAvengers" group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693730817888/b4d8db8e-b055-486b-a53f-b1de22b09313.png align="center")

**Step 6: Verify Access**

Ensure that each of the Avengers DevOps team members can sign in to the AWS Management Console using their IAM user credentials and have the necessary permissions to perform DevOps-related tasks based on the assigned IAM policies.

With these steps, you've created a DevOps team of "Avengers," consisting of three IAM users who are members of the "DevOpsAvengers" group with appropriate IAM policies. Please adjust the policies and permissions according to your specific DevOps requirements and cloud platform if you're not using AWS.

![Apply an IAM password policy on AWS - Taswar Bhatti](https://taswar.zeytinsoft.com/wp-content/uploads/2019/10/aws-iam.png align="left")

**Congrats on your journey so far! 🎉 Don't let excuses hold you back. 🚀 Start with AWS Cloud☁️ and explore its potential. Create IAM users, set up instances, and assemble your DevOps "Avengers" team. 🛠️ Exciting times ahead! 😃**