---
title: "🚀📅 Day 57 DevOps Challenge - 🚀 Launching Your First Kubernetes Cluster with Nginx: A Minikube Adventure! 🛠️"
seoTitle: "launching-your-first-kubernetes-cluster-with-nginx-a-minikube-adventur"
seoDescription: "day-57-devops-challenge-launching-your-first-kubernetes-cluster-with-nginx-a-minikube-adventure"
datePublished: Sat Oct 07 2023 10:05:45 GMT+0000 (Coordinated Universal Time)
cuid: clnfvdtjy000009mqefr4bkcz
slug: day-57-devops-challenge-launching-your-first-kubernetes-cluster-with-nginx-a-minikube-adventure
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696672894078/448f4798-6b72-4401-b7cf-e0ee9c822869.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696672886205/5ca8081e-40dd-4568-b3c6-feb55794b95e.png
tags: web-development, kubernetes, devops, 2articles1week, 90daysofdevops

---

In your previous learning, you gained insights into the architecture of Kubernetes, a fundamental tool in the world of container orchestration. Now, it's time to get hands-on experience and delve into the practical aspects of Kubernetes. We'll start by exploring Minikube, a tool that simplifies setting up a local Kubernetes cluster for development and testing purposes. Let's embark on this exciting adventure! 🌟

## **What is Minikube? 🌐**

Minikube is a powerful tool designed to swiftly set up a local Kubernetes cluster on macOS, Linux, and Windows. It offers the benefits of Kubernetes in a simplified, easy-to-use package, making it an excellent choice for newcomers to the world of containers and developers working on edge computing and IoT projects. Let's uncover the features that make Minikube a go-to option for developers! 🛡️

### **Features of Minikube:**

1. **Supports the latest Kubernetes release**: Minikube supports the latest Kubernetes release, along with six previous minor versions.
    
2. **Cross-platform**: It can be used on Linux, macOS, and Windows.
    
3. **Flexible deployment options**: Minikube can be deployed as a VM, a container, or on bare-metal, offering flexibility based on your needs.
    
4. **Multiple container runtimes**: It supports various container runtimes like CRI-O, containerd, and Docker.
    
5. **Direct API endpoint**: Provides a direct API endpoint for fast image load and build.
    
6. **Advanced features**: Offers advanced features like LoadBalancer, filesystem mounts, FeatureGates, and network policy.
    
7. **Addons for Kubernetes applications**: Easily install Kubernetes applications using addons.
    
8. **Compatibility with common CI environments**: Minikube is compatible with common CI environments, enhancing its usability for developers.
    

## **Installing Minikube on Ubuntu 🐳**

This guide provides step-by-step instructions for installing Minikube on Ubuntu. Minikube allows you to run a single-node Kubernetes cluster locally for development and testing purposes.

### **Task-01: Install Minikube on your local machine or AWS EC2 instance 💻**

To get started, let's install Minikube on your local machine. Before you begin, ensure that you have the following prerequisites:

### **Prerequisites:**

* 2 CPUs or more
    
* 2GB of free memory
    
* 20GB of free disk space
    
* Internet connection
    
* Container or virtual machine manager, such as: Docker, QEMU, Hyperkit, Hyper-V, KVM, Parallels, Podman, VirtualBox, or VMware Fusion/Workstation
    

I'm using an EC2 instance to install and run Minikube.

### **Preparing Your EC2 Instance 🚀**

If you prefer using an EC2 instance for Minikube, ensure that you choose an instance type that meets the requirements:

* **Instance Type**: t2.medium (2 vCPUs, 4 GB RAM)
    

By selecting an EC2 instance with these specifications, you can have a seamless experience running Minikube on AWS.

### **Installation Steps:**

1. **Create an EC2 Instance**: Create a t2.medium EC2 instance on AWS.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669170973/8a849909-0431-41c0-987d-2b5a22a831f3.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669246839/783ee977-481a-45b9-904c-5c632261fb8b.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669323109/49f935f6-9f1a-4b08-bd0c-f950ace93a9f.png align="center")
    
2. **Update and Download kubectl**: Update the instance and download `kubectl` using the following commands:
    
    ```bash
    sudo apt-get update 
    
    ## Download the latest release with the command
    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    
    ## Download the kubectl checksum file
    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
    
    ## Validate the kubectl binary against the checksum file
    echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
    
    ## If valid, the output is: kubectl: OK
    ## Install kubectl
    sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
    
    ## Test to ensure the version you installed is up-to-date:
    kubectl version --client
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669430743/b3e7cb93-3edc-40f1-8802-ba54f090be68.png align="center")
    
3. **Install Docker**: Minikube can run a Kubernetes cluster either in a VM or locally via Docker. This guide demonstrates the Docker method.
    
    * Install**,** Start and enable Docker:
        
        ```bash
        sudo apt install -y docker.io
        sudo systemctl start docker
        sudo systemctl enable docker
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669498229/510b4446-01f9-42a4-a344-7c20fcea50f0.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669534411/fd30c77c-5928-4b1e-a8e9-65aa642261d9.png align="center")
        
    * Add the current user to the docker group (To use Docker without root):
        
        ```bash
        sudo usermod -aG docker $USER && newgrp docker
        ```
        
    * Logout and log back in for the changes to take effect:
        
        ```bash
        exit
        ```
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669570704/ee2f40a2-9387-4435-9bf1-88d81ecf7a2e.png align="center")
        
    * Reconnect to your instance.
        
4. **Install Minikube**: Install Minikube using the following command:
    
    ```bash
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    ```
    

Now you have Minikube installed on your EC2 instance. You can proceed to start Minikube and set up your local Kubernetes cluster.

1. **Start Minikube**: Now, you can start Minikube with the following command:
    
    ```bash
    minikube start --driver=docker
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669646456/efafc597-2f65-41df-81cb-095188d2ced4.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696669831012/d10e563d-11fa-4341-8f14-8a96d2866260.png align="center")
    
    This command will start a single-node Kubernetes cluster inside a Docker container.
    

## **Task-02: Create your first Pod on Kubernetes using Minikube 🏗️**

Now, let's put our knowledge into action and create our first Pod in Kubernetes using Minikube. We'll start by creating an Nginx pod, a popular web server. Let's roll up our sleeves and get our hands dirty with some Kubernetes magic! 🪄

### **Creating an Nginx Pod**

To create an Nginx Pod, follow these steps:

1. Create a YAML configuration file named `pod.yaml` and copy the following content into it:
    
    ```bash
    apiVersion: v1
    kind: Pod
    metadata:
      name: nginx-pod
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696670079212/ec179a48-b62b-4a0d-957b-aeb4b0910c09.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696670102478/d1fd4459-d94c-4acf-8794-b96cce5039d1.png align="center")
    
2. Apply the configuration using the `kubectl` command:
    
    ```bash
    kubectl apply -f pod.yaml
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696670140576/a3a06450-985b-47f4-a3d3-45daee27c8e5.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696670187922/daf218dd-1677-4f39-9795-86b4efa36617.png align="center")
    
    This YAML defines a Pod named `nginx-pod` running the latest version of the Nginx container.
    
3. To access the Nginx Pod, run the following command to access the Minikube VM:
    
    ```bash
    minikube ssh
    ```
    
    Once inside the Minikube VM, you can use `curl` to access the Pod's IP address. Replace `<pod_ip_address>` with the actual IP address of your Pod.
    
    ```bash
    ## To get pod_ip_address run -- kubectl get pods -o wide --
    curl <pod_ip_address>
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696670507189/ee0e5d6f-9758-4368-89c9-c0919c26c61f.png align="center")
    

Congratulations on reaching this exciting milestone in your Kubernetes journey! Stay tuned for more tutorials and insights into the fascinating world of Kubernetes. Happy coding! 🎉