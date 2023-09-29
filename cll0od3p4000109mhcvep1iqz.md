---
title: "🚀📅 Day 7 DevOps Challenge - Streamlining Software Management: The Power of Packages and Package Managers 📦🚀💻"
datePublished: Mon Aug 07 2023 09:33:17 GMT+0000 (Coordinated Universal Time)
cuid: cll0od3p4000109mhcvep1iqz
slug: packages-package-managers-streamline-your-software
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691400606613/42cf12d9-d010-4b34-ad93-476e2484bfe4.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691400783460/d4e92f2f-4e1c-43ec-a4e2-faed03c38485.jpeg
tags: linux, devops, package-manager, 90daysofdevops, shubhamlondhe

---

## **What is a Package?** 📦📂📑💻

A package is a collection of software files and metadata that allows a specific software program or library to be easily installed and managed on a computer system. It acts as a container for all the components necessary to run the software, including executable binaries, libraries, configuration files, documentation, and sometimes even sample data.

## **What is a Package Manager?** 🚀🔧🤖💡🧩

A package manager is a software tool or system that automates the process of installing, updating, configuring, and removing software packages on a computer. These packages, as mentioned earlier, consist of collections of software files and metadata, making it easy to install and manage specific software programs or libraries on a computer system.

## **Different Kinds of Package Managers** 🗂️📦🔍

### Linux Package Managers🐧📦🔍

1. **APT (Advanced Package Tool):** Used in Debian, Ubuntu, and related distributions.
    
2. **YUM (Yellowdog Updater Modified) and DNF (Dandified YUM):** Used in Red Hat Enterprise Linux (RHEL), Fedora, and CentOS.
    
3. **Pacman:** Used in Arch Linux and its derivatives.
    

### Language-Specific Package Managers📦📚🎵

1. **npm (Node Package Manager):** For managing Node.js packages and JavaScript libraries.
    
2. **pip:** For installing Python packages.
    
3. **RubyGems:** For managing Ruby libraries and gems.
    
4. **Composer:** For PHP package management.
    

## Simplified Installation Guide: Docker and Jenkins Using Package Managers on Ubuntu and CentOS 🐳🔧🚀

Installing Docker and Jenkins on your system is now easier than ever, thanks to the power of package managers. Package managers automate the process of software installation and ensure that all dependencies are handled smoothly. In this guide, we will walk you through the steps to install Docker and Jenkins on both Ubuntu and CentOS using their respective package managers. So, let's get started!

### **1\. Installing Docker on Ubuntu using APT**

Docker is a popular platform that allows you to develop, ship, and run applications as lightweight containers. Follow these steps to install Docker on Ubuntu using APT:

**Step 1: Update the package index to ensure you get the latest version of Docker.**

```bash
sudo apt update
```

**Step 2: Install the required dependencies to add the Docker repository to APT.**

```bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

**Step 3: Add Docker GPG key to ensure package integrity during installation.**

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

**Step 4: Add the Docker repository to the APT sources list.**

```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list
```

**Step 5: Update the package index again to include the Docker repository.**

```bash
sudo apt update
```

**Step 6: Install Docker.**

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

**Step 7: Start and enable the Docker service.**

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

### **2\. Installing Jenkins on Ubuntu using APT**

Jenkins is a widely-used automation server that allows you to automate various tasks, including building, testing, and deploying software. To install Jenkins on Ubuntu using APT, follow these steps:

**Step 1: Add Jenkins repository to APT sources list.**

```bash
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

**Step 2: Update the package index to include the Jenkins repository.**

```bash
sudo apt update
```

**Step 3: Install Jenkins.**

```bash
sudo apt install -y jenkins
```

**Step 4: Start and enable Jenkins service.**

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

### **3\. Installing Docker on CentOS using YUM**

For CentOS users, the process is slightly different due to the use of the YUM package manager. Follow these steps to install Docker on CentOS:

**Step 1: Remove any older versions of Docker (if installed).**

```bash
sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine
```

**Step 2: Install the required dependencies.**

```bash
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

**Step 3: Add the Docker repository to the YUM sources list.**

```bash
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

**Step 4: Install Docker.**

```bash
sudo yum install -y docker-ce docker-ce-cli containerd.io
```

**Step 5: Start and enable the Docker service.**

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

### **4\. Installing Jenkins on CentOS using YUM**

Similar to Docker, Jenkins installation on CentOS requires the use of the YUM package manager. Follow these steps:

**Step 1: Add Jenkins repository to the YUM sources list.**

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```

**Step 2: Install Jenkins.**

```bash
sudo yum install -y jenkins
```

**Step 3: Start and enable Jenkins service.**

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

By following the steps outlined in this guide, you have successfully installed Docker and Jenkins on your system using package managers. Docker empowers you to work with containers, while Jenkins offers powerful automation capabilities for your software development process. With these essential tools at your disposal, you can enhance productivity and streamline your software development workflow. 🚀💻

## **Using Package Managers with systemctl and service for Docker and Jenkins** 🐳🔧🚀

**1\. Installing Docker and Jenkins**

Before proceeding, make sure to complete the Docker and Jenkins installation tasks mentioned in the above section. With Docker and Jenkins installed, we can now check the status of the Docker service using the following command:

```bash
sudo systemctl status docker
```

This command will display information about the current state of the Docker service, such as whether it is running, its process ID, and more.

**2\. Controlling Jenkins Service with systemctl**

systemctl is a powerful tool to examine and control the state of the "systemd" system and service manager. Let's explore how we can stop the Jenkins service and view before and after screenshots to witness the change.

***Step 1: Check the current status of the Jenkins service:***

```bash
bashCopy codesudo systemctl status jenkins
```

***Step 2: Capture a screenshot of the output to serve as a "Before" screenshot.***

***Step 3: Stop the Jenkins service using systemctl:***

```bash
sudo systemctl stop jenkins
```

***Step 4: Capture another screenshot of the output to serve as an "After" screenshot.***

Comparing the "Before" and "After" screenshots, you'll notice that the Jenkins service has been successfully stopped.

### Understanding systemctl vs. service: Managing Services in Unix-like Systems 🔧🔍💻

Both systemctl and service are tools used to manage services in Unix-like operating systems. However, they have some differences:

* systemctl: The preferred method for controlling services on systems that use systemd (most modern distributions). It provides more control and features.
    
* service: A legacy command used on older systems that may not use systemd.
    

For example, to check the status of the Docker service using both commands, we can use:

```bash
# Using systemctl
sudo systemctl status docker

# Using service
sudo service docker status
```

In most cases, systemctl is recommended due to its increased capabilities and compatibility with modern systems. 🚀🐧💡

***In conclusion, packages and package managers are 📦 essential tools for smooth software installation and management on computers. A package acts as a container, holding all necessary files, while package managers 🚀 automate the process. Different systems have their own package managers (🐧 APT, YUM, DNF, Pacman) and languages (📚 npm, pip, RubyGems, Composer). Simplified installation guides for Docker and Jenkins on Ubuntu and CentOS showcase the power of package managers 🐳🔧🚀. Embrace packages and package managers to enhance software development productivity! 💻💡***