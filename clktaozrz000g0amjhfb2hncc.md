---
title: "Day 2 DevOps challenge Introduction to Linux and Basic Linux Commands"
seoTitle: "Introduction to Linux and Basic Linux Commands"
datePublished: Wed Aug 02 2023 05:36:14 GMT+0000 (Coordinated Universal Time)
cuid: clktaozrz000g0amjhfb2hncc
slug: day-2-devops-challenge-introduction-to-linux-and-basic-linux-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690954403615/a0713b19-5cc5-426c-af7a-39d21d544b3e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690956575755/5889eef6-c8c7-4a50-bd7d-3573226d53d1.jpeg
tags: linux, beginner, devops, shubhamlondhe, 90daysofdevops-chanllenge

---

## 🐧 **What is Linux?**

Linux 🐧 is a ***powerful*** operating system that has won the hearts of millions worldwide! Unlike other operating systems, Linux is ***open-source***, which means its source code is freely available for anyone to see, modify, and distribute. This makes it a product of collective collaboration, benefiting from the contributions of developers worldwide. 🚀

## 💻 **Why Linux Is Different From Windows?**

When it comes to comparing Linux with Windows, the key distinction lies in its ***open-source*** nature. While Windows is ***proprietary*** and ***closed-source***, Linux's open-source approach fosters a community-driven development model. This enables more rapid **security fixes**, regular updates, and a more **robust** system overall. Additionally, Linux is famously ***lightweight*** and ***efficient***, making it ideal for both older hardware and modern machines, where it runs like a breeze! 💨

## 🧑‍💻 **Components of Linux System:**

Linux is built upon three fundamental components that form the backbone of its functionality. At the core, there's the ***Linux* *kernel***, which acts as the ***brain*** of the system, managing hardware resources, and enabling communication between software and hardware components. On top of the kernel, there's the ***shell***, which provides a ***command-line interface*** for users to interact with the system directly, carrying out tasks with simple commands. Finally, the various ***programs*** and ***software* *applications*** enhance the functionality of Linux, catering to diverse user needs. 🗣️📁🎮

## 🏢 **Architecture Of Linux:**

Understanding the architecture of Linux can be likened to peeling the layers of an exciting tech ***onion!*** At the lowest level, we have the ***hardware layer*** where all the physical components of your computer reside, such as the CPU, RAM, and storage devices. Above that, the ***Linux kernel layer*** manages these hardware resources and provides services to other software components. Lastly, the ***user interface layer*** offers a range of options, from ***command-line interfaces*** for tech-savvy users to ***graphical user interfaces (GUIs)*** for those who prefer a more visual and user-friendly experience. 🖥️

## 🦾 **Benefits of Linux:**

The advantages of using Linux are ***manifold!*** Firstly, it's absolutely ***free***, which is fantastic for ***budget*\-*conscious*** users. The open-source nature of Linux not only encourages community collaboration but also makes it more ***secure*** by allowing continuous scrutiny and improvement. This security aspect is particularly appealing to those concerned about ***privacy*** and protection from cyber threats. Moreover, Linux's ***lightweight*** design ensures that it runs smoothly on a wide range of hardware configurations, making it suitable for both ***older* *computers*** and ***modern machines*.** Lastly, its ***extensive*** ***software repository*** provides a vast array of applications catering to almost any task you can imagine! 🏆

## 💻 **Basic Commands Of Linux:**

Delving into the realm of Linux commands can be an exhilarating experience! With a few keystrokes, you can wield tremendous ***power*** over your system. Some of the most common commands include "***ls***" to list files and folders, "***cd***" to navigate between directories, "***mkdir***" to create new folders, and "***rm***" to delete files. These commands may appear intimidating at first, but once you get the hang of them, they become invaluable tools in your computing ***arsenal***! 📂🔍

\--&gt; Let's learn three essential Linux commands to navigate directories and manage files effectively:

**1\. Check your present working directory**

* **Command:** `pwd`
    
* **Example:**
    
    ```bash
    $ pwd
    /home/user/documents
    ```
    

**2\. List all files or directories, including hidden ones**

* **Command:** `ls -a`
    
* **Example:**
    
    ```bash
    $ ls -a
    .  ..  file1.txt  file2.txt  .hidden_file  directory1  directory2
    ```
    

**3\. Create a nested directory A/B/C/D/E**

* **Command:** `mkdir -p A/B/C/D/E`
    
* **Example:**
    
    ```plaintext
    $ mkdir -p A/B/C/D/E
    ```
    

With these simple commands, you can effortlessly explore your Linux system, organize files, and create nested directories. Embrace the power of the Linux terminal and unleash your productivity! 🐧💻

**Here are some of the most commonly used Linux commands along with a few variations for each:**

### **Essential Linux Commands for Efficient System Navigation and File Management:** 🐧💻

1. `pwd`: Check your present working directory. 📂
    
    * **Example:**
        
        ```bash
        $ pwd
        /home/user/documents
        ```
        
2. `ls`: List files and directories in the current location. 🗂️
    
    * **Example (list with detailed information):**
        
        ```bash
        $ ls -l
        total 32
        drwxr-xr-x 2 user user 4096 Aug  2 10:00 Documents
        drwxr-xr-x 3 user user 4096 Aug  2 09:30 Downloads
        -rw-r--r-- 1 user user  902 Aug  2 10:15 file1.txt
        -rw-r--r-- 1 user user 1203 Aug  2 09:45 file2.txt
        drwx------ 2 user user 4096 Aug  2 09:00 .hidden_folder
        ```
        
    * **Example (list all, including hidden files):**
        
        ```bash
        $ ls -a
        .  ..  Documents  Downloads  file1.txt  file2.txt  .hidden_folder
        ```
        
    * **Example (list only directories):**
        
        ```bash
        $ ls -d */
        Documents/  Downloads/  .hidden_folder/
        ```
        
3. `cd`: Change your directory to a specified path. 🛤️
    
    * **Example (change to a parent directory):**
        
        ```bash
        $ cd ..
        ```
        
    * **Example (change to the home directory):**
        
        ```bash
        $ cd ~
        ```
        
    * **Example (change to a specified path):**
        
        ```bash
        $ cd /home/user/documents
        ```
        
4. `mkdir`: Create a new directory. 📁
    
    * **Example:**
        
        ```bash
        $ mkdir new_folder
        ```
        
5. `rm`: Remove files or directories. ❌
    
    * **Example (remove a file):**
        
        ```bash
        $ rm file1.txt
        ```
        
    * **Example (remove a directory and its contents):**
        
        ```bash
        $ rm -r directory1
        ```
        
6. `cp`: Copy files or directories to a new location. 📋
    
    * **Example (copy a file to a new location):**
        
        ```bash
        $ cp file1.txt /path/to/new_location/
        ```
        
    * **Example (copy a directory and its contents to a new location):**
        
        ```bash
        $ cp -r directory1 /path/to/new_location/
        ```
        
7. `mv`: Move or rename files and directories. 🔄
    
    * **Example (move a file to a new location):**
        
        ```bash
        $ mv file1.txt /path/to/new_location/
        ```
        
    * **Example (rename a file):**
        
        ```bash
        $ mv file1.txt new_name.txt
        ```
        
8. `cat`: Display the content of a file. 📄
    
    * **Example:**
        
        ```bash
        $ cat file1.txt
        This is the content of file1.
        ```
        
9. `grep`: Search for a specific pattern in files. 🔍
    
    * **Example (search for a word in a file):**
        
        ```bash
        $ grep "keyword" file1.txt
        This is the line containing the keyword.
        ```
        
    * **Example (search recursively in multiple files):**
        
        ```bash
        $ grep -r "pattern" /path/to/directory/
        ```
        
10. `chmod`: Change permissions of files and directories. 🔒
    
    * **Example (change file permissions):**
        
        ```bash
        $ chmod +x script.sh
        ```
        
    * **Example (change directory permissions):**
        
        ```bash
        shellCopy code$ chmod 755 directory/
        ```
        

These essential Linux commands will enable you to efficiently manage your files and navigate through your system like a pro! Happy exploring! 🚀💻

## 📖💥 **Summary:**

In ***summary***, Linux is an extraordinary ***open-source*** operating system built on the Linux **kernel**, shaped and refined by a global community of passionate developers. Its ***openness***, ***security***, ***lightweight*** design, and ***extensive software options*** make it a compelling choice for users across the globe. Whether you're a seasoned techie or a curious newcomer, Linux welcomes you with open arms and invites you to experience the ***power*** and ***freedom*** it has to offer! 🐧💻