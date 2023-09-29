---
title: "🚀📅 Day 20 DevOps Challenge - 🚀 Docker Cheatsheet: Essential Commands and Concepts 📋"
seoTitle: "day-20-devops-challenge-docker-cheatsheet-essential-commands-and-conce"
seoDescription: "day-20-devops-challenge-docker-cheatsheet-essential-commands-and-concepts"
datePublished: Sun Aug 20 2023 06:05:09 GMT+0000 (Coordinated Universal Time)
cuid: cllj1niki000409jhdz5u9pho
slug: day-20-devops-challenge-docker-cheatsheet-essential-commands-and-concepts
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692511200711/3d8d7dea-0bab-4d8c-a61f-c50f5600524f.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692511487299/2f96cc2a-c2ba-41ce-be36-c268fce0290a.png
tags: software-development, docker, web-development, devops, 90daysofdevops

---

## **🚀 Introduction**

Docker is a containerization platform that allows developers to package applications and their dependencies into lightweight, portable containers. These containers can run consistently across various environments, from development to production.

## **Installation**

To get started with Docker, you need to install the Docker Engine on your system. Docker provides installation packages for various operating systems.

### **Linux:**

For Linux systems, you can use package managers to install Docker. Below is an example of Ubuntu using `apt`.

Command:

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

### **macOS:**

For macOS, you can use the Docker Desktop application, which provides an easy-to-use interface for managing Docker containers.

Download and install [**Docker Desktop for Mac**](https://www.docker.com/products/docker-desktop).

### **Windows:**

For Windows, you can use the Docker Desktop application, which provides an easy-to-use interface for managing Docker containers.

Download and install [**Docker Desktop for Windows**](https://www.docker.com/products/docker-desktop).

### **Verify Installation:**

After installation, you can verify if Docker is properly installed using the following command:

Command:

```bash
docker --version
```

**Example Output:**

```bash
Docker version 20.10.7, build f0df350
```

Once Docker is installed, you can start using Docker commands to build, run, and manage containers as described in the previous sections of this cheatsheet.

## **📋 General Commands**

* `docker version`: Display Docker client and server version information.
    
    ```bash
    docker version
    ```
    
* `docker info`: Display detailed information about Docker's system-wide configuration.
    
    ```bash
    docker info
    ```
    
* `docker help`: Get help about Docker commands and their usage.
    
    ```bash
    docker help
    ```
    
* `docker --version`: Display the Docker version installed.
    
    ```bash
    docker --version
    ```
    

## **🏗️ Build Images**

To create a Docker image from a Dockerfile:

* `docker build -t <image-name> .`: Build an image from the current directory's Dockerfile.
    
    ```bash
    docker build -t myapp-image .
    ```
    

## **🏃 Run Containers**

To start containers from images:

* `docker run <image-name>`: Run a container from an image.
    
    ```bash
    docker run myapp-image
    ```
    
* `docker run -d <image-name>`: Run a container in detached mode (background).
    
    ```bash
    docker run -d myapp-image
    ```
    
* `docker run -p <host-port>:<container-port> <image-name>`: Map ports between host and container.
    
    ```bash
    docker run -p 8080:80 myapp-image
    ```
    
* `docker run -v <host-path>:<container-path> <image-name>`: Mount volumes between host and container.
    
    ```bash
    docker run -v /host/data:/container/data myapp-image
    ```
    

## **🛠️ Manage Containers**

To manage running containers:

* `docker ps`: List running containers.
    
    ```bash
    docker ps
    ```
    
* `docker ps -a`: List all containers, including stopped ones.
    
    ```bash
    docker ps -a
    ```
    
* `docker start <container-id>`: Start a stopped container.
    
    ```bash
    docker start abc123
    ```
    
* `docker stop <container-id>`: Stop a running container.
    
    ```bash
    docker stop abc123
    ```
    
* `docker restart <container-id>`: Restart a container.
    
    ```bash
    docker restart abc123
    ```
    
* `docker rm <container-id>`: Remove a container.
    
    ```bash
    docker rm abc123
    ```
    

## **📂 Copy to and From Containers**

To copy files between containers and the host:

* `docker cp <local-path> <container-id>:<container-path>`: Copy files from host to container.
    
    ```bash
    docker cp /host/file.txt abc123:/container/
    ```
    
* `docker cp <container-id>:<container-path> <local-path>`: Copy files from container to host.
    
    ```bash
    docker cp abc123:/container/file.txt /host/
    ```
    

## **💻 Execute Commands in Containers**

To run commands inside containers:

* `docker exec -it <container-id> <command>`: Execute a command interactively inside a running container.
    
    ```bash
    docker exec -it abc123 bash
    ```
    

## **📜 Access Container Logs**

To view container logs:

* `docker logs <container-id>`: Display logs of a container.
    
    ```bash
    docker logs abc123
    ```
    
* `docker logs -f <container-id>`: Follow (stream) logs of a container.
    
    ```bash
    docker logs -f abc123
    ```
    

## **📊 View Container Resource Utilization**

To monitor the resource usage of containers:

* `docker stats <container-id>`: Display real-time resource utilization of a container.
    
    ```bash
    docker stats abc123
    ```
    

## **🏞️ Manage Images**

To manage Docker images:

* `docker images`: List local images.
    
    ```bash
    docker images
    ```
    
* `docker rmi <image-id>`: Remove an image.
    
    ```bash
    docker rmi def456
    ```
    
* `docker image prune`: Remove dangling (unused) images.
    
    ```bash
    docker image prune
    ```
    
* `docker image prune -a`: Remove all unused images.
    
    ```bash
    docker image prune -a
    ```
    

## **🚀 Pull and Push Images**

To pull and push images from and to Docker registries:

* `docker pull <image-name>`: Pull an image from a registry.
    
    ```bash
    docker pull myapp-image
    ```
    
* `docker push <image-name>`: Push an image to a registry.
    
    ```bash
    docker push myapp-image
    ```
    

## **🌐 Manage Networks**

To manage Docker networks:

* `docker network ls`: List networks.
    
    ```bash
    docker network ls
    ```
    
* `docker network create <network-name>`: Create a new network.
    
    ```bash
    docker network create my-network
    ```
    
* `docker network connect <network-name> <container-id>`: Connect a container to a network.
    
    ```bash
    docker network connect my-network abc123
    ```
    
* `docker network disconnect <network-name> <container-id>`: Disconnect a container from a network.
    
    ```bash
    docker network disconnect my-network abc123
    ```
    

## **📦 Manage Volumes**

To manage Docker volumes:

* `docker volume ls`: List volumes.
    
    ```bash
    docker volume ls
    ```
    
* `docker volume create <volume-name>`: Create a new volume.
    
    ```bash
    docker volume create my-volume
    ```
    
* `docker volume inspect <volume-name>`: Display detailed info about a volume.
    
    ```bash
    docker volume inspect my-volume
    ```
    
* `docker volume rm <volume-name>`: Remove a volume.
    
    ```bash
    docker volume rm my-volume
    ```
    

## **🏢 Docker Hub Account**

To work with your Docker Hub account:

* Create an account on [**Docker Hub**](https://hub.docker.com/).
    
* `docker login`: Log in to your Docker Hub account.
    
    ```bash
    docker login
    ```
    
* `docker logout`: Log out from your Docker Hub account.
    
    ```bash
    docker logout
    ```
    

## **🧹 Clean Up Unused Resources**

To clean up Docker resources:

* `docker system prune`: Remove stopped containers, unused networks, and dangling images.
    
    ```bash
    docker system prune
    ```
    
* `docker system prune -a`: Remove all unused resources, including images.
    
    ```bash
    docker system prune -a
    ```
    

## **📄 Dockerfile**

A **Dockerfile** is a script used to build a Docker image, specifying a sequence of commands to create a self-contained environment for your application.

Commands:

* `FROM`: Specifies the base image to build upon.
    
* `WORKDIR`: Sets the working directory within the container.
    
* `COPY` or `ADD`: Copies files from the host machine to the container.
    
* `RUN`: Executes commands within the container during the build process.
    
* `CMD` or `ENTRYPOINT`: Specifies the default command to run when a container is started.
    

**Example Dockerfile:**

```bash
# Use an official Python runtime as the base image
FROM python:3.8-slim

# Set the working directory within the container
WORKDIR /app

# Copy application files into the container
COPY . /app

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose a port
EXPOSE 80

# Specify the default command to run the application
CMD ["python", "app.py"]
```

## **🎵 Docker Compose**

**Docker Compose** simplifies managing multi-container applications with a single configuration file (`docker-compose.yml`), defining how various services interact.

Commands:

* `docker-compose up`: Start containers defined in the `docker-compose.yml` file.
    
* `docker-compose up -d`: Start containers in detached mode (background).
    
* `docker-compose down`: Stop and remove containers defined in the `docker-compose.yml` file.
    

**Example** `docker-compose.yml` **for a simple web app and a MySQL database:**

```bash
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:80"
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: example
      MYSQL_DATABASE: myappdb
```

Commands:

* Start containers:
    
    ```bash
    docker-compose up
    ```
    
* Start containers in detached mode:
    
    ```bash
    docker-compose up -d
    ```
    
* Stop and remove containers:
    
    ```bash
    docker-compose down
    ```
    

Remember to create the Dockerfile and docker-compose.yml files in your project directory, and execute the commands in that directory.

**🎉 Conclusion**

Docker simplifies application deployment and management through containerization. This cheat sheet covers essential Docker commands and concepts to get you started with working effectively in Docker environments. Always consult official documentation for the latest details and best practices.