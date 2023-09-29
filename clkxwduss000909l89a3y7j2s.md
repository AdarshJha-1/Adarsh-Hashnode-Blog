---
title: "🚀📅 Day 5 DevOps Challenge - Advanced Linux Shell Scripting for DevOps Engineers with User Management 💻🔒"
seoTitle: "Advanced Linux Shell Scripting for DevOps Engineers with User Manag"
seoDescription: "🚀📅 Day 5 DevOps Challenge - Advanced Linux Shell Scripting for DevOps Engineers with User Management 💻🔒"
datePublished: Sat Aug 05 2023 10:54:30 GMT+0000 (Coordinated Universal Time)
cuid: clkxwduss000909l89a3y7j2s
slug: day-5-devops-challenge-advanced-linux-shell-scripting-for-devops-engineers-with-user-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691232502245/6e54644e-bd84-4c58-bfed-fc64ddb7b5f7.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691232808414/6d2b7cdf-a8e8-4918-bcda-730082e43726.png
tags: linux, devops, shell, 90daysofdevops, shubhamlondhe

---

## 📁📂 **Automate Directory Creation with Bash Scripting! 🐚🚀 Create Dynamic Directories Easily** 📁📂

📝 **Task:** We need to create a bash script called [`createDirectories.sh`](http://createDirectories.sh) that takes three arguments: a directory name, a start number, and an end number. The script will create directories with unique names based on the given range.

📄 **Step 1: Writing the Script**

First, open any text editor and create a new file named [`createDirectories.sh`](http://createDirectories.sh). We'll use this file to write our bash script. Ready? Let's go! ✍️

```bash
#!/bin/bash

# Check if three arguments are provided
if [ "$#" -ne 3 ]; then
  echo "Usage: ./createDirectories.sh <directory_name> <start_number> <end_number>"
  exit 1
fi

# Extract the arguments into variables
directory_name=$1
start_number=$2
end_number=$3

# Loop through the range of numbers and create directories
for ((i = start_number; i <= end_number; i++)); do
  # Create a directory with a dynamic name
  mkdir "${directory_name}${i}"
done

echo "Directories created successfully! 🎉"
```

In this, we use the special variable `$#`, which holds the number of arguments passed to the script. The `if` condition checks if `$#` is not equal to 3. If there are not exactly three arguments, the script displays the usage message and exits. Otherwise, it proceeds with creating the directories as before.

📄 **Step 2: Running the Script**

Now it's time to see our script in action! Open your terminal, go to the directory where you saved [`createDirectories.sh`](http://createDirectories.sh), and run the following commands:

```bash
chmod +x createDirectories.sh
./createDirectories.sh mydir 1 5
```

🎉 Ta-da! The script will create 5 directories named `mydir1`, `mydir2`, `mydir3`, `mydir4`, and `mydir5`.

## 📂📦 **Automated Backup Script: Protect Your Work Effortlessly! 🛡️💾 Simple Bash Script for Data Safety** 📂📦

**📝 Task at Hand:** Our goal is to create a bash script that automatically backs up all your important work. This script will create a compressed archive of your chosen directory and save it to a backup location. With this script, you can relax knowing your efforts are secure! 🛡️💻

**📄 Step 1: Writing the Script** Let's start by opening your favorite text editor and creating a new file called `backup_script.sh`. We'll use this file to write our backup script. Ready? Let's get started! ✍️🚀

```bash
#!/bin/bash

# Set the source directory to back up
source_directory="/path/to/your/work/directory"
# Set the backup destination
backup_destination="/path/to/backup/location"
# Create a unique backup file name with date and time
backup_file_name="backup_$(date '+%Y%m%d_%H%M%S').tar.gz"
# Create the backup archive
tar -czf "$backup_destination/$backup_file_name" "$source_directory"

echo "Backup completed successfully! 📦🎉"
```

**📄 Step 2: Understanding the Script** Let's break down the script we just wrote:

1. We set the `source_directory` variable to the path of the directory you want to back up. Replace `/path/to/your/work/directory` with the actual path to your work directory.
    
2. We set the `backup_destination` variable to the location where you want to store the backup file. Replace `/path/to/backup/location` with the desired backup storage location.
    
3. We create a unique backup file name using the current date and time. This way, each backup will have a different name, making it easy to identify and organize multiple backups.
    
4. The `tar` command compresses the contents of the source directory into a gzipped archive with the specified name and saves it to the backup destination.
    
5. Finally, we display a message to let you know that the backup process was successful! 🎉
    

**📄 Step 3: Running the Script** With the script ready, let's run it to perform our first backup! Open your terminal, navigate to the directory where you saved `backup_script.sh`, and execute the following commands:

```bash
chmod +x backup_script.sh
./backup_script.sh
```

## 🔄 Automating Backup with Cron & Crontab🗄️

### **💡 What is Cron?**

Cron is like a scheduler 📆 for your computer! It allows you to set up automatic tasks 🔄, like backups 🗄️, that run at specific times or intervals. It's commonly used in Unix-like systems to keep things organized and save you time ⏰. By using Cron, you can focus on other things while it handles repetitive tasks 🤖.

### 💡 What is Crontab?

Think of Crontab as the command center 🎛️ for Cron. It's where you create and manage your scheduled tasks. Each user has their own Crontab file, and you can easily edit it using simple commands. By using Crontab, you take control of when your tasks run, making it easy to manage your automated processes 🚀.

**✍️ How to Set Up Cron & Crontab:**

1. Create a file and paste this code:
    

```bash
#!/bin/bash
a=$(date +%y-%m-%d-%H-%M-%S)
touch /home/ubuntu/$a.deb
```

This script will create a backup file with a timestamp in its name.  
**Manage cron jobs:**

1. View existing jobs: `crontab -l`
    
2. Set up a new task: `crontab -e` and add schedule.
    
3. Check cron status: `sudo service cron status`
    
4. Start cron service: `sudo service cron start`
    
5. Stop a specific job: `crontab -e`, then delete the line.
    

## 📝 User Management : Creating and Managing Users

Hey there! 🙌 Ready to learn about User Management? It's like having a bouncer for your computer 🕺, controlling who gets in and who doesn't! Let's dive in:

### 🚀 What's User Management?

Think of it as the "gatekeeper" 🚧 of your computer. It handles user accounts 🙎‍♂️🙎‍♀️, deciding who can access what. Super crucial for security! You wouldn't want random strangers peeking at your stuff, right? 🔒

### 🙋‍♂️ Who's a User?

A user is like a VIP 🎩 in the Linux world! They can do stuff like a magician 🪄—manipulate files, perform tricks (commands), and more! Each user has a special ID 🔢 that's unique to them. Root user 👑 gets ID 0, and system users get IDs 1 to 999. But for regular local users, IDs start from 1000. Keep it organized and exclusive! 💼

***let's create two users and set passwords for them on Linux:***

1. **Open a terminal.**
    
2. **To create the first user, type the following command and press Enter:**
    

```bash
sudo adduser user1
```

set a password for the user1:

Type `sudo passwd user1`

Then, give a new password and retype the new password.

Then, your password was updated for the user1 successfully

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687854979580/2fe60b49-3084-48ca-8933-585de813e5c3.png?auto=compress,format&format=webp align="center")

1. **To create the second user, type the following command and press Enter:**
    

```bash
sudo adduser user2
```

similarly, you can set a password for user2 also.

1. **To display the usernames of the created users, type the following command and press Enter:**
    

```bash
cut -d: -f1 /etc/passwd
```

You will see a list of usernames displayed on the screen, including "user1" and "user2."