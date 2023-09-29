---
title: "🚀📅 Day 31 DevOps Challenge - AWS and IAM Basics ☁: Automating EC2 Instance Configuration"
datePublished: Mon Sep 04 2023 09:06:23 GMT+0000 (Coordinated Universal Time)
cuid: clm4nqdab000n09mp4fcm2jly
slug: day-31-devops-challenge-aws-and-iam-basics-automating-ec2-instance-configuration
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693818177940/f412e20b-2573-4d65-81ca-d82656f9f0ab.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693818372171/b575c00a-1970-4501-adb2-2c2380e26454.jpeg
tags: aws, web-development, devops, jenkins, 90daysofdevops

---

## **Chapter 1: Welcome to Our AWS Journey 🚀**

Welcome back to our AWS journey! By now, you've likely become familiar with Amazon Web Services (AWS) and have created several EC2 instances. If you've manually installed applications like Jenkins, Docker, or Apache on these instances, you might be wondering if there's a more efficient way to manage and automate these tasks. Well, you're in luck because in this blog, we'll delve into some AWS basics, specifically focusing on EC2 user data and AWS Identity and Access Management (IAM). So, fasten your seatbelts, as we dive into the world of automation in the cloud! 🚀

### **A Quick Recap: What is AWS? ☁**

Amazon Web Services (AWS) is a cloud computing platform that offers a wide range of services and resources for building, deploying, and managing applications in the cloud. AWS has gained immense popularity due to its scalability, reliability, and flexibility, making it a top choice for businesses and individuals alike. If you're just getting started with AWS, don't forget that they offer a free tier, perfect for students and cloud enthusiasts to explore and experiment with the platform without incurring costs.

📣 **Important Point:** You can Read Day-30 Blog post to learn more about AWS and IAM. [**Click Here**](https://adarshdevops.hashnode.dev/day-30-devops-challenge-getting-started-with-aws-basics) for Day-30 Blog Post. 🌟

## **Chapter 2: EC2 User Data: Streamlining Instance Configuration 🛠️**

When you launch an EC2 instance in AWS, you have the option to provide user data. User data is a powerful feature that allows you to automate various configuration tasks and execute scripts after an instance starts. This eliminates the need for manual intervention every time you launch an instance and want to install applications like Apache, Docker, Jenkins, or any other software. Let's break down some key aspects of EC2 user data:

### **Types of User Data**

There are two primary types of user data you can pass to an EC2 instance:

1. **Shell Scripts**: These are simple scripts written in shell languages like Bash. You can use them to perform a wide range of tasks, from software installation to system configuration.
    
2. **Cloud-Init Directives**: Cloud-init is a popular multi-distribution package that handles early initialization of cloud instances. It can interpret cloud-init directives written in YAML format to configure your instance.
    

### **Ways to Pass User Data**

You have several options for providing user data to an EC2 instance:

* **Plain Text**: You can enter user data directly in the launch instance wizard when creating an instance using the AWS Management Console.
    
* **File**: If you're launching instances using command-line tools, you can save your user data in a file and provide the file path during instance creation.
    
* **Base64-encoded Text**: For API calls, you can encode your user data in base64 format. This is useful when automating instance launches through scripts.
    

By leveraging user data, you can ensure that your EC2 instances are automatically configured to your desired state as soon as they start. This streamlines the deployment process and reduces manual effort significantly.

## **Chapter 3: IAM: Managing Access Securely 🔐**

While automating EC2 instance configuration is fantastic, it's equally important to ensure the security of your AWS resources. This is where AWS Identity and Access Management (IAM) comes into play. IAM is a web service that enables you to securely control access to your AWS resources. Here are some key points to understand about IAM:

### **Centralized Permissions**

With IAM, you can centrally manage permissions that dictate which AWS resources users can access. This helps you maintain control and security across your entire AWS environment.

### **Authentication and Authorization**

IAM handles both authentication (signing in) and authorization (permissions) for users. This means you can determine not only who can access AWS resources but also what actions they can perform on those resources.

IAM plays a crucial role in securing your AWS infrastructure, especially in multi-user or multi-team environments. It ensures that only authorized personnel can access and modify your cloud resources, reducing the risk of security breaches.

In conclusion, AWS provides powerful tools like EC2 user data and IAM to simplify and secure your cloud operations. By automating instance configuration and managing access permissions effectively, you can make the most of AWS's capabilities while maintaining a strong security posture. So, whether you're a student exploring the AWS free tier or a cloud enthusiast looking to optimize your cloud workflows, these AWS basics are essential for your journey into the cloud. Stay tuned for more AWS adventures! ☁🔐🚀👩‍💻

## **Task 1: Launch EC2 Instance with Jenkins**

### Step 1: Launching EC2 Instance

1. **Log In to AWS Console:** Sign in to your AWS account.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693813493635/4d1d1c4e-859a-4cdb-856c-c221766da82e.png align="center")
    
2. **Navigate to EC2:** Click on "Services" &gt; "EC2" under the "Compute" section.
    
3. **Launch an Instance:**
    
    * Click "Instances" in the left-hand menu.
        
    * Click "Launch Instance."
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693813529083/8a8a5d76-b879-4607-8818-e7e250edff66.png align="center")
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814020237/deea3313-351d-4421-8cb6-5f9ca95f7d8c.png align="center")
    
4. **Choose an Amazon Machine Image (AMI):**
    
    * In the "Search for an AMI" field, type "Ubuntu."
        
    * Select an Ubuntu AMI that suits your needs. Ensure that you choose an Ubuntu version that's compatible with Jenkins.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693813956890/f2eaad19-ca0f-4e51-abf6-e089b960a914.png align="center")
        
5. **Configure Instance:**
    
    * Select the instance type that suits your needs. For a basic Jenkins setup, a t2.micro instance should suffice.
        
    * Skip other configuration steps for simplicity.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814079494/ba370a70-3dd6-4d37-b84f-21c0f7b0f27f.png align="center")
        
6. **Add Storage:** Use the default settings or configure as needed.
    
7. **Access Key Pair:**
    
    * Choose an existing key pair or create a new one.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814123843/130eb876-6553-469a-94b1-19da3ebafe4b.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814172119/4b831974-1ea0-4d22-a703-f0c386b0e4a5.png align="center")
        
    * Download and save the key pair for SSH access.
        
8. **Launch the Instance:**
    
    * Click "Launch Instances."
        

### Step 2: SSH into the EC2 Instance

1. **Wait for the Instance to Launch:**
    
    * Monitor the instance status until it's "running."
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814413681/fa6ae538-6ea7-4920-ac3c-f27bd94101bf.png align="center")
        
2. **Get the Public IP Address:**
    
    * Note the public IP address from the EC2 dashboard.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814450209/ef1dc3ae-2412-4225-9d31-83b508fefc91.png align="center")
        
3. **Open Terminal (or SSH Client):**
    
    * Use a terminal or SSH client to connect to the EC2 instance. Replace `YOUR_PUBLIC_IP` with your instance's IP address and `YOUR_KEY.pem` with the path to your private key file:
        
    
    ```bash
    sudo ssh -i YOUR_KEY.pem ubuntu@YOUR_PUBLIC_IP
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814578764/cfae11dd-a6f2-4115-b503-5829e006e4ce.png align="center")
    

### Step 3: Install Jenkins

1. **Update the Package List:**
    
    * Run the following command to update the package list:
        
    
    ```bash
    sudo apt-get update
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693814641968/4a90064d-46e9-4288-ade8-0733365f6476.png align="center")
    
2. **Install Jenkins:**
    
    * Execute the following commands to install Jenkins:
        
    
    ```bash
    # Install Java
    ## Description
    ## Jenkins is built on Java, so it requires Java Runtime. Java Runtime is being installed before Jenkins to ensure compatibility."
    sudo apt install -y openjdk-17-jre
    
    # Install Jenkins
    wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt-get update
    sudo apt-get install -y jenkins
    
    # Start Jenkins
    sudo systemctl start jenkins
    sudo systemctl enable jenkins
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693815028486/eb9ae511-48e0-47ff-882e-cb8a1afd8b0e.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693815075418/eced4de6-0f5a-46f4-aaaa-9ed35fe50224.png align="center")
    

### Step 4: Accessing Jenkins from the Web

Please be patient as Jenkins completes its installation process.

**Access Jenkins Dashboard:**

1. Open your preferred web browser.
    
2. In the address bar, enter the following URL: [`http://YOUR_PUBLIC_IP:8080`](http://YOUR_PUBLIC_IP:8080) (Make sure to replace "YOUR\_PUBLIC\_IP" with the actual public IP address of your instance).
    
3. Press Enter to navigate to the Jenkins dashboard.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693815248230/04924064-d8a2-4f46-8ada-084ab74b5358.png align="center")

If you encounter an issue where the Jenkins dashboard does not open, it might be because your Amazon EC2 instance's security group or firewall rules do not allow traffic on port 8080, which is the default port Jenkins runs on. Let's resolve this issue:

**Allow Port 8080 Access on EC2:**

To enable access to Jenkins on port 8080, follow these steps:

1. Log in to your AWS Management Console.
    
2. Navigate to the EC2 dashboard.
    
3. Click on "Instances" in the left navigation pane and select your Jenkins instance.
    
4. In the instance details panel, locate and click on the "Security" tab.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693815902002/052a549e-3158-4305-a524-512ff4f09a97.png align="center")
    
5. Find the security group associated with your instance (usually named something like "launch-wizard-1").
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693815944053/e1cb2ec5-0c4c-43ec-8215-494af5bf9d22.png align="center")
    
6. Click on the security group to view its details.
    
7. In the "Inbound rules" tab, click "Edit inbound rules."
    
8. Click "Add rule."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693815993103/b5111b0c-b282-4319-8511-5e00e06370cd.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693816032847/f62c0495-5dc6-4083-afc0-414887c4158c.png align="center")
    
9. Configure the rule as follows:
    
    * Type: Custom TCP Rule
        
    * Protocol: TCP
        
    * Port Range: 8080 (This is the default Jenkins port)
        
    * Source: 0.0.0.0/0 (This allows access from anywhere, which may not be the most secure option. Adjust it according to your security needs.)
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693816084686/87f67999-ad6b-4a05-bce9-410e76865523.png align="center")
        
10. Click "Save rules."
    
11. Now, you should be able to access the Jenkins dashboard at [`http://YOUR_PUBLIC_IP:8080`](http://YOUR_PUBLIC_IP:8080) without any issues.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693816162842/b82b785d-6c62-4851-b1c5-4601685170c4.png align="center")
    

Remember to terminate the instance when you're done to avoid additional charges.

## **Task 2: Creating IAM Roles and Explaining IAM Users, Groups, and Roles**

### IAM Users, Groups, and Roles Explanation:

**IAM Users:** IAM stands for Identity and Access Management. In AWS (Amazon Web Services), IAM Users are individual entities that represent people, services, or applications that need access to AWS resources. Users have their own unique credentials (username and password) or can use temporary security credentials to sign in and interact with AWS services. Each user can have specific permissions assigned to them, dictating what they can and cannot do within your AWS environment.

**IAM Groups:** IAM Groups are collections of IAM Users. Instead of assigning permissions to each user individually, you can organize users into groups and assign permissions to the group. This makes it easier to manage permissions for multiple users with similar roles or responsibilities. When you add a user to a group, they inherit the group's permissions.

**IAM Roles:** IAM Roles are a way to grant permissions to AWS resources, like EC2 instances or Lambda functions, rather than individual users or groups. Roles are meant to be assumed by trusted entities, and they provide temporary credentials to those entities. This is particularly useful in scenarios where you want to grant permissions to AWS services or applications without hardcoding credentials, enhancing security and manageability.

### **Creating IAM Roles:**

Now, let's create the three IAM Roles you mentioned: DevOps-User, Test-User, and Admin. We'll do this using the AWS Management Console.

**Step 1: Sign in to the AWS Management Console**

* Go to the AWS Management Console ([**https://aws.amazon.com/console/**](https://aws.amazon.com/console/)).
    
* Sign in with your AWS account credentials.
    

**Step 2: Navigate to IAM**

* Click on "Services" in the top left corner.
    
* Under "Security, Identity, & Compliance," select "IAM" (Identity and Access Management).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817058445/f1b94570-718f-44e7-a2cf-bfa349771915.png align="center")
    

**Step 3: Create the DevOps-User Role**

* In the IAM dashboard, click on "Roles" in the left-hand menu.
    
* Click the "Create role" button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817114084/b10c1ef3-29c8-4de1-8e53-a0055083857c.png align="center")
    
* Select "AWS service" as the type of trusted entity.
    
* Choose the use case that best describes your scenario. For example, if you want this role for an EC2 instance, select "EC2" under "Select your use case."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817207468/1b0e901d-fce4-4180-a2f2-2fc0737e33df.png align="center")
    
* Click "Next: Permissions" and attach the necessary permissions policies.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817320039/c2c6b9a1-6294-4ce4-bafe-4aedaedba08c.png align="center")
    
* Name the role "DevOps-User" and provide a description if needed.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817358782/70b4a61f-4072-4fb4-b444-d47dc5fbcbd2.png align="center")
    
* Review the role settings and click "Create role."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817425087/21f5ae5b-503d-4036-bb79-9cf30001ce36.png align="center")
    

**Step 4: Create the Test-User Role and Admin Role**

* Repeat the above steps (Step 3) twice, once for the "Test-User" and once for the "Admin" role.
    
* Customize the permissions policies and descriptions according to the specific roles and their responsibilities.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693817529857/51c4a88f-f7bc-4086-ac32-14ab184fafbd.png align="center")
    

**Learn AWS basics 🌐, automate tasks with user data scripts 🤖, and secure access with IAM 🔒. Task 1: Launch an EC2 instance with Jenkins 🚀 and verify by taking screenshots 📸. Task 2: Understand IAM roles, users, groups, and create specific roles 🤓. Get started on your cloud journey! ☁️**