---
title: "🚀📅 Day 55 DevOps Challenge - Creating a VPC and Launching a Website on AWS Using Terraform"
datePublished: Wed Oct 04 2023 06:58:52 GMT+0000 (Coordinated Universal Time)
cuid: clnbedxy1000909mae3yidi8a
slug: day-55-devops-challenge-creating-a-vpc-and-launching-a-website-on-aws-using-terraform
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696402634218/e4461b79-b418-4ba1-b1e4-61b0ddc3226d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696402640771/1bd5999e-480f-41be-8a59-c87564a9702f.png
tags: aws, web-development, devops, 2articles1week, 90daysofdevops

---

Welcome to our guide on creating a Virtual Private Cloud (VPC) and launching a website on Amazon Web Services (AWS) using Terraform. In this tutorial, we will walk you through the process of setting up a VPC, and subnets, launching an EC2 instance, and hosting a simple website.

## **Step 1: Set up the VPC and Subnets**

First, let's set up the foundation of our infrastructure - the VPC and its associated subnets.

We'll use Terraform to define the infrastructure as code and create the VPC with the desired CIDR blocks.

```bash
terraform {
    required_providers {
        aws = {
            source = "hashicorp/aws"
            version = "5.19.0"
        }
    }
}
provider "aws" {
    region = "ap-south-1"
}
resource "aws_vpc" "example" {
    cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "public" {
    vpc_id                  = aws_vpc.example.id
    cidr_block              = "10.0.1.0/24"
}

resource "aws_subnet" "private" {
    vpc_id                  = aws_vpc.example.id
    cidr_block              = "10.0.2.0/24"
}
```

## **Step 2: Set up Internet Connectivity**

Next, we need to set up internet connectivity by creating an Internet Gateway (IGW) and associating it with the VPC.

```bash
resource "aws_internet_gateway" "example" {
  vpc_id = aws_vpc.example.id
}
```

## **Step 3: Configure Route Table and Associate with Public Subnet**

We need to configure a route table for the public subnet and associate it to enable internet access.

```bash
resource "aws_route_table" "public" {
  vpc_id = aws_vpc.example.id

  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.example.id
  }
}

resource "aws_route_table_association" "public" {
  subnet_id      = aws_subnet.public.id
  route_table_id = aws_route_table.public.id
}
```

## **Step 4: Create a Security Group**

```bash
resource "aws_security_group" "web" {
  vpc_id = aws_vpc.example.id

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
  ingress {
    from_port   = 22
    to_port     = 22
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

## **Step 5: Launch an EC2 Instance**

Now, let's launch an EC2 instance in the public subnet and set it up to host a simple website.

```bash
resource "aws_instance" "webserver" {
    ami           = "ami-0f5ee92e2d63afc18"
    instance_type = "t2.micro"
    availability_zone = "ap-south-1b"
    subnet_id     = aws_subnet.public.id

    user_data = <<-EOF
                #!/bin/bash
                sudo apt update -y
                sudo apt install nginx -y
                EOF

    vpc_security_group_ids = [aws_security_group.web.id]
}
```

## **Step 6: Create an Elastic IP and Associate with the EC2 Instance**

Lastly, let's create an Elastic IP and associate it with the EC2 instance for a static public IP.

```bash
resource "aws_eip" "example" {
    domain = "vpc"
    instance = aws_instance.webserver.id
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400197368/cb68f723-50fb-4e4b-9047-a2bf2523875d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400218092/0c44e614-6563-45bf-8a79-809d5b5dd860.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400234845/8da8f2d0-535c-4418-9002-b6ebbf6c5046.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400398902/22658ff4-38bb-436b-8d08-de79baf76fec.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400428400/d82ae239-d118-4aaa-8a4c-8ade3402e954.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400461987/7f976ad3-130d-4eba-b17b-d925839259a7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400482264/19917a4e-0552-44d7-a936-9a98d3cba3a8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400506437/18a2d2de-73d1-4ccd-a794-12c45659ce42.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400533313/5fa86030-c375-4a1e-9ab0-b60553a5fd02.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400562118/aea4f543-c9a4-4456-92e8-2c84758fed5c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400582313/5ae7a289-3933-43e1-8096-e94f0b1b8fd5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400639374/86c56f9c-16ba-4996-9988-77aaa87a14bc.png align="center")

## **Step 7: Verification**

After applying the Terraform configuration, visit the website hosted on the EC2 instance by opening the Elastic IP in a web browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400677062/432f1f9b-06cf-45fe-ab3f-e70e48a40b0b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400696356/3a6d2035-3abb-472e-818a-4ebfae2e84ff.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400742620/a2416258-2217-4c76-bed1-6a0496d6c32d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696400775777/30dd8e7f-de2c-4a79-b7d3-04129875b758.png align="center")

Congratulations! You have successfully created a VPC, set up subnets, launched an EC2 instance, and hosted a website on AWS using Terraform. This infrastructure is scalable and can serve as a starting point for more complex setups and applications. Happy coding!