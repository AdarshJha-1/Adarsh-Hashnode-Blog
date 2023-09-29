---
title: "🚀📅 Day 36 DevOps Challenge - ⚡️ Unleashing the Power of Relational Database Service in AWS ⚡️"
datePublished: Sat Sep 09 2023 08:35:04 GMT+0000 (Coordinated Universal Time)
cuid: clmbrtcr8000l0al2aqqz26dh
slug: day-36-devops-challenge-unleashing-the-power-of-relational-database-service-in-aws
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694242346002/483a48f4-c98d-4cb4-8baa-171b784214c0.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694248488293/2e45b50f-9fb2-47ac-8a12-962c6328f599.jpeg
tags: aws, web-development, devops, aws-rds, 90daysofdevops

---

## **Introduction 🌐**

In today's fast-paced digital world, data is the lifeblood of many organizations. Storing, managing, and scaling databases efficiently are essential for businesses to thrive. This is where Amazon Relational Database Service (Amazon RDS) steps in as a game-changer. In this blog, we'll explore the world of Amazon RDS, its core features, benefits, and why it's become an indispensable tool for businesses operating in the cloud.

## **What is Amazon RDS? 🛢️**

**Amazon RDS** is a fully managed database service offered by **Amazon Web Services (AWS)**. It provides a scalable and cost-effective solution for setting up, operating, and managing relational databases in the cloud. With Amazon RDS, you can use popular database engines like MySQL, PostgreSQL, Oracle, SQL Server, and MariaDB without the hassle of infrastructure management.

![Amazon RDS](https://www.awsgeek.com/Amazon-RDS/Amazon-RDS.jpg align="left")

## **Key Features of Amazon RDS 🛠️**

### **1\. Managed Service 🤖**

Amazon RDS takes care of routine database tasks such as provisioning, patching, backup, recovery, and scaling, allowing you to focus on your applications and data.

### **2\. Multiple Database Engines 💽**

It supports a wide range of database engines, enabling you to choose the one that best suits your application requirements.

### **3\. High Availability 🌐**

Amazon RDS offers automated failover, backup, and recovery, ensuring that your databases are highly available and reliable.

### **4\. Scalability 📈**

You can easily scale your database up or down based on your workload needs, with options for both vertical and horizontal scaling.

### **5\. Security 🔒**

Amazon RDS provides robust security features, including network isolation, encryption at rest and in transit, and fine-grained access control through AWS Identity and Access Management (IAM).

### **6\. Monitoring and Metrics 📊**

You can monitor your database performance using Amazon CloudWatch, set up alarms, and gain insights into resource utilization and database health.

![What is AWS RDS?](https://www.infosectrain.com/wp-content/uploads/2023/04/Advantages-of-AWS-RDS.jpg align="left")

## **Benefits of Amazon RDS 🌟**

### **1\. Simplified Database Management 🧹**

With Amazon RDS, you don't need to worry about database administration tasks. AWS takes care of the heavy lifting, allowing you to focus on application development.

### **2\. Cost Efficiency 💰**

You pay only for the resources you use, and you can easily adjust the database size to match your workload, which can lead to significant cost savings.

### **3\. High Availability and Durability 🛡️**

Amazon RDS automatically replicates your database across multiple Availability Zones, ensuring data durability and minimizing downtime.

### **4\. Security and Compliance 🔐**

AWS provides a secure and compliant environment for your databases, helping you meet industry standards and regulations.

### **5\. Scalability 🚀**

You can seamlessly scale your database vertically (by increasing CPU and RAM) or horizontally (by adding read replicas) to handle increased workloads.

### **6\. Global Reach 🌍**

Amazon RDS supports cross-region replication, allowing you to deploy databases in multiple regions for disaster recovery and low-latency access for users worldwide.

## **Use Cases for Amazon RDS 📦**

Amazon RDS is suitable for a wide range of use cases, including:

1. **Web Applications**: Hosting databases for web applications that require flexibility, scalability, and reliability.
    
2. **E-commerce**: Managing product catalogs, customer data, and order processing systems.
    
3. **Content Management**: Storing and delivering content efficiently for content management systems (CMS).
    
4. **Data Warehousing**: Analyzing large datasets for business intelligence and reporting.
    
5. **Gaming**: Managing player profiles, game progress, and in-game transactions.
    

## Task-01**: Setting Up an AWS RDS MySQL Instance, EC2 Instance, IAM Role, and MySQL Client Connection**

In this guide, we will walk you through the process of setting up a Free Tier RDS (Relational Database Service) instance of MySQL, creating an EC2 (Elastic Compute Cloud) instance, configuring an IAM (Identity and Access Management) role with RDS access, and connecting your EC2 instance to the RDS MySQL server using a MySQL client. Follow these steps carefully:

### **Step 1: Create a Free Tier RDS Instance of MySQL**

1. Log in to your AWS Management Console.
    
2. Navigate to the AWS RDS service.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694242839138/302b17c8-629c-48f5-80a9-ec6948d130ac.png align="center")
    
3. Click on "Create database."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694242880669/817d61a9-4372-4887-8164-37acebda42d1.png align="center")
    
4. Choose "MySQL" as the database engine.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694242934922/a7b5bfc3-2c39-4f32-8677-0b9ae682164f.png align="center")
    
5. Select the "Free tier" template for the RDS instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694242967969/5dbcbc3c-6e15-400b-a458-a561d0ea9908.png align="center")
    
6. Configure your database settings, such as instance size, storage, username, and password. Make note of these credentials; you'll need them later.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243033692/2093382a-60dd-41ea-94ee-e0fc93329b6d.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243190347/06d97a3f-67c7-48f0-b527-aa996ebc8ad6.png align="center")
    
7. Configure your database's security settings, including VPC (Virtual Private Cloud) and security group settings.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243307972/7823402f-a17d-4988-a1f5-6a024047f1bf.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243348980/ed516d48-aa26-4ddf-b1dd-4887777fe4f7.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243699320/c433a4a4-efad-4f67-8f1a-e7627388b3d4.png align="center")
    
8. Review your configuration and click "Create database."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243903630/3ff62068-21f9-4bd3-851e-044729848771.png align="center")
    
9. Wait for the RDS instance to be created and become available.
    

### **Step 2: Create an EC2 Instance**

1. Navigate to the AWS EC2 service.
    
2. Click on "Launch Instance."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694243956403/7e8ebb5e-41ab-4960-bd42-7c0309110531.png align="center")
    
3. Choose an Amazon Machine Image (AMI) and instance type for your EC2 instance.
    
4. Create or select an existing key pair for SSH access and save it securely.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244002495/8847b560-e741-4a95-a1e4-e4764f7f86a2.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244035651/cfff058a-fca1-46de-bfc9-8e7398e247a9.png align="center")
    
5. Configure instance details like the number of instances, network settings, and storage.
    
6. Configure security groups to allow inbound traffic on the MySQL port (default is 3306).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244197716/27611f7c-a9b7-404a-bf8d-f8ce6cd0bd52.png align="center")
    
7. Review your instance configuration and launch the EC2 instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244288817/7bdb75eb-05f6-4c3e-ae57-b01645a55215.png align="center")
    

### **Step 3: Create an IAM Role with RDS Access**

1. Navigate to the AWS IAM service.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244311198/1a64bf09-db99-4c6f-bfdd-2b93d3f795ca.png align="center")
    
2. Click on "Roles" in the left navigation pane.
    
3. Click "Create role."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244359093/a64bfba9-0d03-4731-a406-86e120d0b92f.png align="center")
    
4. Select "EC2" as the trusted entity type.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244429859/35446117-fa49-46e1-850f-1bceea551150.png align="center")
    
5. Attach a policy that grants RDS access to the role, such as "AmazonRDSFullAccess" or create a custom policy.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244485912/493b7b5b-a1aa-4809-ac5d-83e52a1d69cf.png align="center")
    
6. Review and name your role, then click "Create role."
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244557013/c89f4be3-ff39-4dc4-8b4c-91d464f8e114.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244587193/ac9431c0-6deb-400b-9c09-76e7fb80f42e.png align="center")

### **Step 4: Assign the IAM Role to EC2**

1. Go back to the EC2 dashboard.
    
2. Select your EC2 instance.
    
3. Click "Actions" and choose "Security" then "Modify IAM role"
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244865592/fd06d88e-618f-4bb5-acfa-4a237999304a.png align="center")
    
4. Select the IAM role you created earlier and confirm the attachment.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694244889624/81bebc99-fb36-4d64-afa9-d520428d1c4e.png align="center")
    

### **Step 5: Set Up EC2 Connection with MySQL RDS**

1. **Go to RDS:** Log in to your AWS Management Console and navigate to the AWS RDS service.
    
2. **Select Your Database:** From the RDS dashboard, select the RDS instance associated with your MySQL database.
    
3. **Access EC2 Connection Setup:** In the RDS instance details page, click on the "Database" section on the left sidebar. Then, under the "Instance actions" dropdown, select "Set up EC2 connection."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694247029377/761157e6-9a5d-4f4e-9303-5d35b1df073f.png align="center")
    
4. **Choose an EC2 Instance:** In the "Set up EC2 connection" wizard, you will see a list of available EC2 instances in your AWS account. Choose the EC2 instance that you want to associate with the RDS instance for direct connectivity.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694247064578/e969ff39-a955-48dd-b6bf-75eb62ee37ad.png align="center")
    
5. **Press Continue:** After selecting the EC2 instance, press the "Continue" button to proceed.
    

By following these steps, you are associating the chosen EC2 instance with your RDS instance, allowing for direct network connectivity between them. This can be useful when you want to establish more secure and efficient communication between your EC2 instance and RDS database, bypassing the public internet.

### **Step 6: Connect EC2 to RDS Using MySQL Client**

1. SSH into your EC2 instance using the key pair you saved during the EC2 instance setup.
    
    ```bash
    ssh -i your-key-pair.pem ec2-user@your-ec2-instance-ip
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694245003652/a6c5ff61-cc0b-45bc-b862-cf650c95d710.png align="center")
    
2. Update your EC2 instance by running:
    
    ```bash
    sudo apt update -y
    ```
    
3. Install the MySQL client on your EC2 instance:
    
    ```bash
    sudo apt install mysql-server -y
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694245301820/51d023b0-c631-4a87-b6fc-01bd15cb4a75.png align="center")
    
4. Connect to your RDS MySQL instance using the credentials you noted in Step 1:
    
    ```bash
     mysql -h <endpoint address> -P <port.no> -u <username> -p
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694247106616/ebd2a2a8-373e-493c-8bfa-4a75001f4cc9.png align="center")
    
5. Enter the MySQL password when prompted.
    
6. You are now connected to your RDS MySQL instance via your EC2 instance using the MySQL client.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694246593627/b57f1d2c-5d4a-4628-9b5b-7ebc2b7cee07.png align="center")
    

Congratulations! You've completed the setup of an RDS MySQL instance, an EC2 instance, and an IAM role with RDS access, and successfully connected your EC2 instance to the RDS MySQL server using a MySQL client. This demonstrates your ability to configure AWS services for database access and EC2 instance connectivity.

## **Conclusion 🎉**

Amazon Relational Database Service (Amazon RDS) has revolutionized the way organizations manage their databases in the cloud. Its managed services, scalability, security, and cost-efficiency have made it a preferred choice for businesses of all sizes. By offloading database management tasks to AWS, you can free up resources to innovate and drive your business forward while ensuring your data is secure, available, and performant.

Whether you're launching a startup, running a mission-critical application, or simply seeking a more efficient way to manage your databases, Amazon RDS is undoubtedly a service worth considering on your AWS journey. It's time to embrace the power of Amazon RDS and take your database management to the next level in the cloud. ☁️