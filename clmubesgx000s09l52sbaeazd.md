---
title: "🚀📅 Day 46 DevOps Challenge - Exploring Ansible Ad-hoc Commands: A Quick and Efficient Automation Tool 🚀"
datePublished: Fri Sep 22 2023 08:03:28 GMT+0000 (Coordinated Universal Time)
cuid: clmubesgx000s09l52sbaeazd
slug: day-46-devops-challenge-exploring-ansible-ad-hoc-commands-a-quick-and-efficient-automation-tool
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695369543673/b62c3753-efa8-4c48-905b-0500a661f071.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1695369800475/86eeacd8-cf89-4d20-bef1-bc61c59b7e9d.avif
tags: aws, web-development, devops, 2articles1week, 90daysofdevops

---

Welcome back to our Ansible learning journey! Today, we'll dive into understanding ad-hoc commands in Ansible. Ad-hoc commands are one-liners designed to achieve very specific tasks, making them like quick snippets or a compact Swiss army knife when you want to perform quick tasks across multiple machines.

## **Ansible Ad-hoc Commands vs. Playbooks**

To simplify, Ansible ad-hoc commands are analogous to one-liner Linux shell commands, while playbooks are akin to shell scripts—a collection of many commands with logic and structure.

Ad-hoc commands shine when you need to execute a quick task without the need for a more comprehensive playbook.

![Ansible Boot Camp 4 — Playbooks. Ansible boot camp series | by Tony | Geek  Culture | Medium](https://miro.medium.com/v2/resize:fit:1352/1*PUxKAyI4hog1mNdldI5d0g.png align="center")

**Ansible Playbooks**:

* Comparable to a well-structured recipe, comprising multiple steps and ingredients.
    
* Suited for orchestrating complex, multistep tasks with conditional logic and error handling.
    

**Ansible Ad-hoc Commands**:

* Like whipping up a quick snack, requiring minimal ingredients and preparation.
    
* Ideal for rapid, straightforward tasks on the fly.
    

## **Task 1: Exploring Ad-hoc Commands**

Let's delve into a practical example to understand the efficiency of Ansible ad-hoc commands. For this demonstration, we'll consider a setup with three EC2 instances: one for the Ansible master server and two for the target servers.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695367725317/40a1ae25-0be6-4685-a304-56e40ab0ef9c.png align="center")

### **Embracing Secure Automation: SSH Key-Based Authentication 🗝️**

Before we proceed, let's prioritize security. **SSH key-based authentication** is a fundamental security measure. We highly recommend setting it up between your control machine and the hosts. This ensures a secure and streamlined authentication process, eliminating the need for credentials for each command or playbook execution. It's akin to having a trusted key to effortlessly open doors.

If you haven't set up SSH key-based authentication yet, there are abundant resources available to guide you through this secure authentication setup. If you need guidance on setting up SSH key-based authentication, you can read about SSH connections or passwordless authentication on my [**Day-45-blog-about-Ansible**](https://adarshdevops.hashnode.dev/day-45-devops-challenge-understanding-configuration-management-with-ansible) for a detailed walkthrough.

With SSH key-based authentication in place, we can now proceed to harness the power and simplicity of Ansible ad-hoc commands for seamless automation! 🚀

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695368345822/e518b05e-1cd0-4723-8916-3cd3cd081989.png align="center")

### **Example 1: Pinging Servers 🛰️**

Imagine you want to check the connectivity to several servers. The Ansible ad-hoc `ping` command allows us to achieve this swiftly.

```bash
ansible all -i inventory_file -m ping
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695368533043/09df2be5-06b7-4ad9-a5e7-145b88866ba5.png align="center")

In this command:

* `ansible`: The Ansible command-line tool.
    
* `all`: Specifies the target hosts (in this case, all hosts defined in the inventory).
    
* `-i inventory_file`: Specifies the inventory file containing the host information.
    
* `-m ping`: Utilizes the `ping` module to ping the hosts.
    

Replace `inventory_file` with the actual path to your inventory file.

### **Example 2: Checking Uptime ⏰**

Now, let's consider monitoring the uptime of the servers using an ad-hoc command.

```bash
ansible all -i inventory_file -a "uptime"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695368608746/1769ad32-7e4b-41f1-9659-25ef4f43c3a6.png align="center")

In this command:

* `ansible`: The Ansible command-line tool.
    
* `all`: Specifies the target hosts (all hosts defined in the inventory).
    
* `-i inventory_file`: Specifies the inventory file containing the host information.
    
* `-a "uptime"`: Uses the `-a` flag to pass the command to the target hosts, executing the `uptime` command.
    

### **Example 3: Checking Free Memory Usage 🧠**

Monitoring memory usage is crucial for system performance. Here's how you can check the free memory or memory usage of hosts using an Ansible ad-hoc command.

```bash
ansible all -i inventory_file -a "free -m"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695368843115/96ea1353-eb53-4d7d-87a3-10a631778fe8.png align="center")

In this command:

* `ansible`: The Ansible command-line tool.
    
* `all`: Specifies the target hosts (all hosts defined in the inventory).
    
* `-i inventory_file`: Specifies the inventory file containing the host information.
    
* `-a "free -m"`: Uses the `-a` flag to pass the `free -m` command to the target hosts, displaying memory usage.
    

For practicing more such commands, you can learn and practice from [**Ansible\_AD\_HOC\_Command**](https://www.middlewareinventory.com/blog/ansible-ad-hoc-commands/).

## **Conclusion**

Understanding Ansible ad-hoc commands is essential for efficiently managing and automating tasks across multiple machines. They provide a quick and convenient way to perform specific actions without the need for elaborate playbooks. We've covered a simple ping command and checking uptime, showcasing the power and simplicity of Ansible ad-hoc commands. Stay tuned for more Ansible insights and tutorials! 🎉

Stay tuned for more Ansible insights and tutorials! 🎉 Happy automating! 💻