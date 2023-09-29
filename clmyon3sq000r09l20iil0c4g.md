---
title: "🚀📅 Day 48 DevOps Challenge - Ansible Project: Deploying a Web App with Ansible 🔥"
datePublished: Mon Sep 25 2023 09:24:56 GMT+0000 (Coordinated Universal Time)
cuid: clmyon3sq000r09l20iil0c4g
slug: day-48-devops-challenge-ansible-project-deploying-a-web-app-with-ansible
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695633797763/882d7946-543d-4c7f-b17b-02c120555e7c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1695633883946/3fcdd8fb-fe61-424e-b1f4-5c869f73de01.png
tags: web-development, devops, hashnode, 2articles1week, 90daysofdevops

---

Welcome to this exciting Ansible project where we'll explore the power of Ansible playbooks by deploying a simple web app. In this project, we'll follow a step-by-step approach to create EC2 instances, set up Ansible, and use it to install and deploy a web application using Nginx.

## **Task 01: Setting Up the Environment 🛠️**

### **Step 1: Create 3 EC2 Instances**

To start, we'll create 3 EC2 instances using the same key pair. These instances will serve as our web servers.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630066728/a317b5f7-f9aa-44ce-9d6f-a9e3fbe8cfeb.png align="center")

### **Step 2: Install Ansible on the Host Server**

Next, on the host server, we'll install Ansible, a powerful automation tool that will help us manage and configure our EC2 instances.

```plaintext
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630633128/f0b7ff73-9799-48aa-a0dc-68cc3bdc96bb.png align="center")

### **Step 3: Configure SSH Key for Passwordless Authentication 🗝️**

We'll generate an SSH key pair on our Ansible master server using `ssh-keygen`. We will then copy the public key, stored in `~/.ssh/id_rsa.pub`, to the target server's `~/.ssh/authorized_keys` file. This approach enables passwordless authentication and facilitates easy access to the target server.

\--&gt; In master server

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630707344/3d5d4f06-cc4d-4acd-b468-b357cf1b04c8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630729729/c0bc8d22-e59f-4710-9c4c-c873e51d230a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630764201/a9f00628-0cf8-4b14-83e2-0b78e512f18f.png align="center")

\--&gt; In target server-1

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630974070/e3164178-e229-4e44-acc7-89bcc686c37e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695630994955/34c8665e-8c4a-42e8-ba14-0e080a034214.png align="center")

\--&gt; In target server-2

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695631062671/26e6f2e7-5cce-43c8-a4e8-ec7063863735.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695631095032/b958097d-71a5-417d-b120-aa2e2b3246cc.png align="center")

### **Step 4: Access the Inventory File**

We'll access the Ansible inventory file using a text editor (here we'll use `sudo vim /etc/ansible/hosts`) to define the IP addresses of our EC2 instances. This file is crucial for Ansible to know which servers to manage.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695631400185/517dd75b-01be-421c-8ce1-c8dc3e1cb17d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695631527810/bbf2b345-0e41-456b-b145-9691f226100e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695631573216/44c7b6e4-2672-4202-b9e5-c378a67847b0.png align="center")

## **Task 02: Creating Ansible Playbook 📘**

### **Step 1: Create a Playbook to Install Nginx**

We'll create an Ansible playbook, which is a YAML file defining the tasks Ansible will perform. Our playbook will include tasks to install Nginx, a popular web server, on the EC2 instances.

```plaintext
---
- name: Install Nginx
  hosts: all  # Specify the group of EC2 instances in your inventory
  become: true  # Run tasks with elevated privileges

  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present

    - name: Start Nginx service
      service:
        name: nginx
        enabled: yes
        state: started
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632178771/223dcf3a-c3be-42ff-9d2f-a3da8181f4b5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632198389/810f9d3d-8aad-427b-a55e-89741902acdc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632208413/89c97f51-23d4-4855-add4-937e52198b01.png align="center")

### **Step 2: Deploy a Sample Webpage**

We'll extend our Ansible playbook to deploy a sample webpage using Nginx.

```plaintext
---
  tasks:
    # Previous tasks remain unchanged

    - name: Create HTML directory
      file:
        path: /var/www/html
        state: directory

    - name: Create index.html file
      copy:
        content: "<html><body><h1>Hello, Ansible! 🚀</h1></body></html>"
        dest: /var/www/html/index.html
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632570309/ec32bd8d-0d72-4f54-918e-9b3135a067dd.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632581879/4940e7e7-376f-485b-9fe6-d735d0927056.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632618083/6a828917-fdc7-487c-9e68-51d247ccf80a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632668504/30702cb6-6f21-4315-904a-6e9c28481ece.png align="center")

\--&gt; target server-1

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632801589/41419490-7399-4b71-a5c2-aeb27f6f5167.png align="center")

\--&gt; target server-2

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695632810300/c1d0eb4d-e3e8-4d3c-8938-d2cd2ac3655f.png align="center")

So, in addition to the method we just covered, there's another way to achieve this. We can create an `index.html` file with the necessary source code. Additionally, we'll create a playbook to perform this particular task. like this :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695633693584/e3a6b2e3-b534-49a2-8d04-19c215e203aa.png align="center")

## **Conclusion 🎉**

By completing this Ansible project, you've gained hands-on experience in automating server setup and application deployment. Ansible is a powerful tool that can be leveraged for various automation tasks in a system administration role. Explore further and adapt this project to suit your specific needs and applications. Happy automating! 🔥