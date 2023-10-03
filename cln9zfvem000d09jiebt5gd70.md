---
title: "🚀📅 Day 54 DevOps Challenge - Working with Terraform Resources 🚀"
datePublished: Tue Oct 03 2023 07:12:42 GMT+0000 (Coordinated Universal Time)
cuid: cln9zfvem000d09jiebt5gd70
slug: day-54-devops-challenge-working-with-terraform-resources
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696317084759/6d6200e5-f772-4ee5-a06b-ba3f3c395d08.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696317154739/4ff357a0-9a91-4c03-b490-b8728ed4d53d.png
tags: aws, web-development, devops, 2articles1week, 90daysofdevops

---

In our previous blog post, we explored the basics of creating a Terraform script using Blocks and Resources. Today, we will delve deeper into Terraform resources and understand how they play a vital role in defining and managing components of your infrastructure.

## **Understanding Terraform Resources**

Terraform resources represent key components of your infrastructure, such as physical servers, virtual machines, DNS records, S3 buckets, and more. These resources possess attributes that define their properties and behaviors, such as size, location, or domain name.

When defining a resource in Terraform, you specify its type, a unique name, and the attributes that characterize it. Terraform utilizes the resource block to define these resources within your Terraform configuration.

## **Setting Up** [`main.tf`](http://main.tf) File and Provider Block

Before we start creating resources, let's set up the [`main.tf`](http://main.tf) file and define the Terraform block along with the provider block for AWS. 🏗️

### **Step 1: Create** [`main.tf`](http://main.tf)

Create a file named [`main.tf`](http://main.tf) and open it in your preferred text editor.

### **Step 2: Define Terraform Block**

Add the Terraform block to specify the required version of Terraform:

```bash
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "5.19.0"
    }
  }
}
```

### **Step 3: Define Provider Block for AWS**

Next, define the provider block for AWS. If you've configured AWS CLI using `aws configure` on your system, Terraform will automatically use those credentials. **Note**: It's a best practice to use IAM roles or environment variables for your credentials rather than hardcoding them in your configuration files.

```bash
provider "aws" {
  region = "ap-south-1"
}
```

Replace `"ap-south-1"` with your desired AWS region.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696222931582/bcbdf925-6d4e-40f1-a942-5ca970f83e9b.png align="center")

Now that we have set up our Terraform configuration file and provider block, let's proceed to create a security group and an EC2 instance using Terraform. 🛠️

## **Task 1: Create a Security Group**

To allow traffic to the EC2 instance, a security group needs to be created. Let's follow these steps:

### **Step 1: Add Security Group Configuration**

In your [`main.tf`](http://main.tf) file, add the following code to create a security group:

```bash
resource "aws_security_group" "web_server" {
  name_prefix = "web-server-sg"

   ingress {
        from_port   = 80
        to_port     = 80
        protocol    = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
    }
    ingress {
        from_port   = 443  
        to_port     = 443  
        protocol    = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
    }
    egress {
        from_port   = 0  
        to_port     = 0
        protocol    = "-1"  
        cidr_blocks = ["0.0.0.0/0"]
    }
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316302777/7c9ea5dc-879b-43ea-87ea-028dcd1aa8d2.png align="center")

### **Step 2: Initialize and Apply**

Run `terraform init` to initialize the Terraform project. Then, execute `terraform apply` to create the security group. 🛠️

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696223367353/ac79e365-b23c-4958-a14b-967c8b0bb648.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696223593478/70fdf7ac-4cbc-4884-aefa-ee396c34736e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696223621709/15a39709-5293-46c4-bdd5-e7f8fc7ad48e.png align="center")

## **Task 2: Create an EC2 Instance**

Now, let's proceed to create an EC2 instance using Terraform:

### **Step 1: Add EC2 Instance Configuration**

In your [`main.tf`](http://main.tf) file, append the following code to create an EC2 instance:

```bash
resource "aws_instance" "web_server" {
  ami           = "ami-0557a15b87f6559cf"
  instance_type = "t2.micro"
  key_name      = "my-key-pair"
  security_groups = [
    aws_security_group.web_server.name
  ]

  user_data = <<-EOF
                    bin/bash
                    sudo apt update
                    sudo apt install nginx -y
                    sudo systemctl start nginx
                    sudo systemctl enable nginx
              EOF
}
```

Note: Replace the `ami` and `key_name` values with your own. Refer to the AWS documentation for a list of available AMIs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316633655/cea935f7-e9b1-48b9-a2fd-a2df22bdbe0e.png align="center")

### **Step 2: Apply Configuration**

Run `terraform apply` to create the EC2 instance. 🚀

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316464005/6d4eabad-996d-40d7-a916-4dd50f285f5d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316487145/c65d1296-968f-45cc-a7c1-ad90116e45f9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316500139/3c1cdd12-ef08-48ed-b19c-2edd4f5e0062.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316746165/c8194689-5424-4c14-915d-8581c5734e18.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696316815512/c037e28a-0d33-4514-8fc1-cfaff41e8e4a.png align="center")

Stay tuned for more exciting Terraform tutorials and insights on managing your infrastructure effortlessly! 🌟