---
title: "🚀📅 Day 51 DevOps Challenge - Terraform and Docker: A Match Made in Automation Heaven 🚀✨"
datePublished: Thu Sep 28 2023 09:15:48 GMT+0000 (Coordinated Universal Time)
cuid: cln2ymx5l000g08if465r2pr4
slug: day-51-devops-challenge-terraform-and-docker-a-match-made-in-automation-heaven
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695892437311/7ff6b41b-f870-4c86-8e21-621f3987deef.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1695892492188/e948e17d-a4f0-42dc-a7de-20547a0c0480.png
tags: web-development, devops, hashnode, 2articles1week, 90daysofdevops

---

In today's journey through the realm of infrastructure automation, we delve into the dynamic duo of Terraform and Docker. Let's harness their powers to streamline and manage our resources efficiently. 💪

## **Terraform Provider Configuration**

Terraform requires explicit instructions on the provider to use for automation. Here, we are using Docker as our provider. To do this, we set up the provider with a specific source and version in our main Terraform configuration file ([main.tf](http://main.tf)). 🔧

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695888483397/96dcdd31-49e0-415c-a1b6-4b09d3f3161a.png align="center")

```bash
terraform {
  required_providers {
    docker = {
      source = "kreuzwerker/docker"
      version = "3.0.2"
    }
  }
}
```

Note: `kreuzwerker/docker` is shorthand for [`registry.terraform.io/kreuzwerker/docker`](http://registry.terraform.io/kreuzwerker/docker). 🚀

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695888937410/f5fc82d6-a3c6-4285-bea4-025c2259bfeb.png align="center")

### **Provider Block**

The provider block configures the specified provider, in this case, Docker. A provider in Terraform is a plugin used to create and manage your resources.

```bash
provider "docker" {}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695888952991/1dcb4c5a-388e-4c6c-8230-613c6b2a990c.png align="center")

## **Terraform Resource Blocks**

Resource blocks define components of your infrastructure. These components could be physical or virtual, such as a Docker container, or they could be logical, like a Heroku application.

Each resource block specifies the resource type and a unique resource name.

## **Task-01: Creating a Terraform Script with Blocks and Resources**

Let's create a Terraform script with Blocks and Resources. 🛠️

#### Resource Block for Docker Image (nginx)

```bash
resource "docker_image" "nginx" {
  name         = "nginx"
  keep_locally = false
}
```

#### Resource Block for Running a Docker Container (nginx)

```bash
resource "docker_container" "nginx" {
  image = docker_image.nginx.name
  name  = "nginx-conatiner"
  ports {
    internal = 80
    external = 80
  }
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695890804276/6d00b03e-d627-4222-aa0c-5a144fce82ae.png align="center")

### **Task-02: Running Terraform Commands**

Follow these steps to initialize Terraform, plan the changes, and apply the configuration:

1. **Initialize Terraform**:
    
    Navigate to the directory where your Terraform configuration ([main.tf](http://main.tf)) is located and run the following command to initialize Terraform and download the required provider plugins:
    
    ```bash
    terraform init
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695889455799/e4e9f035-f475-42b2-8ebc-9f38704709ab.png align="center")
    
2. **Plan the Changes**:
    
    Run the following command to see what changes Terraform will apply to your infrastructure:
    
    ```bash
    terraform plan
    ```
    
    This will provide a summary of the actions Terraform will take. 📋
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695890921034/1e6344c2-6a12-443f-b432-bbdcc5853d5a.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695890944458/6aa3fd59-f62f-4434-b9a4-6fb84d67ed05.png align="center")
    
3. **Apply the Configuration**:
    
    Once you've reviewed the plan and are ready to apply the changes, run the following command:
    
    ```bash
    terraform apply
    ```
    
    Terraform will prompt you for confirmation. Type `yes` and hit Enter.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695890989342/511dd4e2-28df-42e0-ae75-93aa1686846d.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695891006307/d2a7a635-41b5-4464-851e-3331c862cea8.png align="center")
    
4. **Check if the Container is Created**:
    
    After applying the configuration, check if the Docker container (nginx) is successfully created by running:
    
    ```bash
    sudo docker ps -a
    ```
    
    This command will list all containers, and you should see the newly created container named "nginx-container". 🐳
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695891336802/b07e5ef0-8188-4cea-999b-f7c647d67902.png align="center")
    
5. **Check NGINX Running Inside the Container**:
    
    To verify if the NGINX server is running inside the Docker container and accessible on your [localhost](http://localhost), open a web browser or use a tool like curl or your web browser to access NGINX via the exposed port (port 80):
    
    ```bash
    curl http://localhost:80
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695891392885/60cb1db2-a1ee-4171-a26a-400ce860ea2b.png align="center")
    
    or open a web browser and navigate to:
    
    ```bash
    http://localhost:80
    ```
    
    If NGINX is running successfully inside the Docker container, you should see the default NGINX landing page or content.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695891628455/31284afa-60f2-4029-856b-ed2b4ba52de1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695891645752/8ddafd36-3ec7-4181-ba1c-ffec61a149d1.png align="center")

With this step, we've confirmed that NGINX is running inside the Docker container and is accessible on your [localhost](http://localhost) through port 80.

## **Task-03: Docker Installation (In case Docker is not installed)**

If Docker is not installed on your system, follow these steps: ⚙️

```bash
sudo apt-get update
sudo apt-get install docker.io -y
docker --version
```

With this foundation of Terraform and Docker, we're equipped to orchestrate and manage our infrastructure effectively. Stay tuned for more exciting automation adventures! 🚀🐳

*In summary, today's journey unveiled the symbiotic power of Terraform and Docker, enhancing resource management. Mastering the Terraform provider setup and resource blocks is key to successful automation. Execute with confidence using Terraform commands, and watch your Docker containers come to life seamlessly! 🔥🚀🐳*

**Thanks for reading my blog!**

Let's connect with each other. Here's my [**LinkedIn**](https://www.linkedin.com/in/adarsh2005/) and [**Twitter**](https://twitter.com/adarshjha__1). Feel free to reach out, and let's continue the discussion. 🙌