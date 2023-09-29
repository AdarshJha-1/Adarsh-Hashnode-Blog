---
title: "🚀📅 Day 47 DevOps Challenge - Automating Server Management with Ansible Playbooks 🚀"
datePublished: Sun Sep 24 2023 07:21:21 GMT+0000 (Coordinated Universal Time)
cuid: clmx4sbor000008l249c5gmtd
slug: day-47-devops-challenge-automating-server-management-with-ansible-playbooks
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695540000250/32e1151d-f004-40b6-9bec-d576f849c676.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1695540035168/427aeae0-ca20-4f42-ad62-9f9044047295.png
tags: aws, ansible, devops, 2articles1week, 90daysofdevops

---

## **Ansible Playbooks**

Welcome to Day 47 of our journey into the world of Ansible, a powerful and efficient automation tool. Today, we will explore Ansible playbooks, which serve as instruction manuals to automate various tasks, assign roles, define configurations, and deploy applications across multiple servers. Ansible playbooks are essential for streamlining and organizing tasks efficiently, especially when dealing with a fleet of servers. In this blog, we'll dive into creating playbooks for three specific tasks: creating a file on a different server, adding a new user, and installing Docker on a group of servers.

![How to Write an Ansible Playbook. - Ansible Tutorial - Digital Varys](https://i0.wp.com/digitalvarys.com/wp-content/uploads/2020/04/image-7.png?fit=1024%2C518&ssl=1 align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537064925/61085489-6367-4abd-abd1-6f4c1f008d29.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537091962/39bf8072-ad11-41e0-9443-dac016aca6cc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537229575/fb4dd5ea-0ee0-4488-b8c7-7c8f9cfc8535.png align="center")

### **Task-01: Creating a File on a Different Server**

To create a file on a different server using Ansible, we need to define a playbook with the necessary steps. Let's create a playbook named `create_file.yml`:

```yaml
---
- name: Create a file on a different server
  hosts: all
  become: true
  tasks:
    - name: Create a file
      file:
        path: /home/ubuntu/file.txt
        state: touch
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537515768/471a1ee7-5894-4acb-a20f-cd196f59e494.png align="center")

You can run this playbook using the **ansible-playbook** command Replace `inventory_file` with the path to your inventory file.

```yaml
ansible-playbook -i inventory_file create_file.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537801776/975b8dd5-d080-48a7-81c7-df00c01111ed.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537827683/f71024ec-0d7e-494b-a7c9-2fd3e5dc4fbf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695537851568/a06cb44c-1ca7-47b3-b82d-3b81b10c2767.png align="center")

### **Task-02: Creating a New User**

Creating a new user using Ansible involves defining a playbook. Let's create a playbook named `create_user.yml` for this task:

```yaml
---
- name: Create a new user
  hosts: target_server
  tasks:
    - name: Add a new user
      user:
        name: new_user
        state: present
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538503193/3c687ed7-bc39-4051-8fe5-9c3eb9c9f9ff.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538097020/59b94783-bd19-419a-82fa-43e02484c623.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538285449/9ce36a0c-5e00-47aa-b3d7-316ae1b48e25.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538304375/59bc1f0f-e806-479a-a030-5aec839f0c15.png align="center")

### **Task-03: Installing Docker on a Group of Servers**

Installing Docker on a group of servers involves defining a playbook. Let's create a playbook named `install_docker.yml` for this task:

```yaml
---
- name: Install Docker on a group of servers
  hosts: docker_servers
  tasks:
    - name: Install Docker
      apt:
        name: docker.io
        State: present
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538712990/06bd16bd-9e5e-4539-8852-02b83bfaaec9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538687941/e7f2ae73-d8c7-40cc-9d2e-32b4fe6a798e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695538768496/d3d34c12-8ec9-4fa9-929f-1898c5b267dd.png align="center")

Ansible playbooks are incredibly powerful and versatile, allowing us to automate a wide range of tasks across multiple servers with ease and efficiency. Whether it's creating files, adding users, or installing applications like Docker, Ansible playbooks serve as indispensable tools in the realm of automation, streamlining operations, and saving valuable time for system administrators and developers alike.

# **Writing Efficient Ansible Playbooks: Best Practices for Automation Success 🚀**

Ansible is a powerful open-source automation tool that allows you to automate IT infrastructure management. Ansible playbooks are the configuration files that describe the desired state of your systems. Writing Ansible playbooks with best practices can make your automation more robust, reliable, and scalable. In this blog, we will discuss some best practices for writing Ansible playbooks.

### **1\. Use a Clear Structure**

Make sure your playbook is organized and easy to read. Use comments and section headers to explain what each part of the playbook does. Avoid nesting too many tasks or plays inside each other, as it can make the playbook difficult to read and maintain.

```yaml
---
- name: Install Apache Web Server
  hosts: webservers
  become: yes
  
  tasks:
    - name: Ensure Apache web server is installed
      apt:
        name: apache2
        state: latest
    
    - name: Start Apache service
      service:
        name: apache2
        state: started
        enabled: yes
```

### **2\. Use Idempotent Tasks**

Idempotency is one of the key principles of Ansible. It means that a task should be designed in such a way that it can be executed repeatedly without changing the state of the system. This makes your playbook more robust and prevents unexpected changes to the system. You can achieve idempotency by using modules that are designed to be idempotent, such as apt, yum, and copy.

```yaml
---
- name: Install Apache web server
  apt:
    name: apache2
    state: latest
```

### **3\. Use Variables**

Variables can make your playbook more flexible and reusable. They allow you to store values that can be used across multiple tasks and playbooks. You can define variables in the playbook itself or in separate files, such as group\_vars or host\_vars.

```yaml
---
- name: Install Nginx web server
  apt:
    name: nginx
    state: latest

- name: Configure Nginx web server
  template:
    src: nginx.conf.j2
    dest: /etc/nginx/nginx.conf
  vars:
    nginx_port: 80
```

### **4\. Use Roles**

Roles are a way to organize your tasks, variables, and files into reusable components. They can be used across multiple playbooks and provide a way to share functionality between different teams. Roles can also make your playbook more modular and easier to maintain.

```yaml
---
- name: Install web server
  hosts: all
  roles:
    - webserver
```

### **5\. Use Tags**

Tags allow you to selectively run specific tasks or groups of tasks within a playbook. This can be useful when testing or debugging your playbook or when you need to run a subset of tasks. Tags can be added to individual tasks or to entire plays.

```yaml
---
- name: Install web server
  hosts: all
  become: yes
  tags:
    - webserver

  tasks:
    - name: Install Apache web server
      apt:
        name: apache2
        state: latest
      tags:
        - apache

    - name: Install Nginx web server
      apt:
        name: nginx
        state: latest
      tags:
        - nginx
```

### **6\. Use Conditionals**

Conditionals allow you to execute a task only if a specific condition is met. This can be useful when you need to run a task only on a subset of hosts or when you need to run a task only if a specific variable is defined.

```yaml
---
- name: Example playbook with a conditional
  hosts: all
  vars:
    myvar: "tmp"
  tasks:
    - name: Task 1
      debug:
        msg: "This task will always run"

    - name: Task 2
      debug:
        msg: "This task will run if myvar equals 'tmp'"
      when: myvar == "tmp"
```

By following these best practices, you can write efficient, modular, and maintainable Ansible playbooks that can be easily adapted to different environments and situations. Happy automating! 🛠️

**Thanks to our readers! For more insightful content, follow me on** [**LinkedIn**](https://www.linkedin.com/in/adarsh2005/) **and explore my blogs on** [**Hashnode**](https://adarshdevops.hashnode.dev/)**. Stay updated and keep learning! 🌟**