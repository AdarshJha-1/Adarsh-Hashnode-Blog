---
title: "🚀📅 Day 12 DevOps Challenge - Master Linux, Git & GitHub: Your Ultimate Cheat Sheet 🐧🐙🚀"
seoTitle: "linux-git-github-cheat-sheet"
seoDescription: "linux-git-github-cheat-sheet"
datePublished: Sat Aug 12 2023 06:36:25 GMT+0000 (Coordinated Universal Time)
cuid: cll7n8wng000609mi2x6kd3by
slug: linux-git-github-cheat-sheet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691821690682/6a65b362-66b6-48c9-8f2b-d841ca2fc28e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691821785306/23b3b01c-c1f4-4085-97d3-f3077b586735.png
tags: software-development, web-development, devops, 90daysofdevops, shubhamlondhe

---

# **Linux Commands Cheat Sheet 🐧**

## Everyday Linux Commands: Boost Your Productivity 🐧💼

**Navigation:**

* `cd [directory]`: Change directory. 🚀
    
* `pwd`: Print working directory. 📂
    
* `ls [options] [path]`: List files and directories. 🗂️
    
* `mkdir [directory]`: Create a new directory. 📁
    
* `rmdir [directory]`: Remove an empty directory. 🗑️
    

**File Operations:**

* `touch [filename]`: Create an empty file. ✨
    
* `cp [source] [destination]`: Copy files/directories. 📝
    
* `mv [source] [destination]`: Move/Rename files/directories. 🔄
    
* `rm [options] [file/directory]`: Remove files/directories. ❌
    

**File Permissions:**

* `chmod [permissions] [file]`: Change file permissions. 🔒
    
* `chown [user:group] [file]`: Change file ownership. 👥
    

**Text Manipulation:**

* `cat [file]`: Display file contents. 🐱
    
* `less [file]`: View file content interactively. 📖
    
* `head [file]`: Display the beginning of a file. 📄
    
* `tail [file]`: Display the end of a file. 📑
    
* `grep [pattern] [file]`: Search for patterns in a file. 🔍
    
* `wc [file]`: Count lines, words, and characters. 🧮
    

**Process Management:**

* `ps`: Display running processes. 🔄
    
* `kill [PID]`: Terminate process by PID. ☠️
    
* `killall [process_name]`: Terminate processes by name. ☠️
    
* `top`: Monitor system processes. 📈
    

**System Information:**

* `uname -a`: Display kernel info. 🐧
    
* `df -h`: Show disk space usage. 💽
    
* `free -h`: Display RAM usage. 🧠
    
* `ifconfig`: View network config. 🌐
    

**User Management:**

* `whoami`: Display current username. 👤
    
* `id`: Show user/group info. 👨‍👩‍👦
    
* `users`: List logged-in users. 🧑‍💻
    
* `passwd`: Change user password. 🔑
    

**File Searching:**

* `find [path] [expression]`: Search for files/dirs. 🔍
    
* `locate [filename]`: Find files using the database. 🔍
    

**Archive & Compression:**

* `tar [options] [archive_name.tar] [files/dirs]`: Create/extract tar archives. 🗃️
    
* `gzip [file]`: Compress using gzip. 🗜️
    
* `gunzip [file]`: Decompress with gzip. 🗜️
    
* `zip [archive_name.zip] [files/dirs]`: Create a zip archive. 📦
    
* `unzip [archive_name.zip]`: Extract from zip. 📦
    

**Networking:**

* `ping [host]`: Send ICMP echo requests. 🏓
    
* `ssh [user@]host`: Securely connect with SSH. 🔒
    
* `scp [source] [destination]`: Copy over SSH. 📤📥
    
* `wget [url]`: Download from the web. 🌐🔽
    
* `curl [url]`: Transfer with URLs. 🌐🔗
    

**Disk & Filesystem:**

* `df -h`: Show disk space usage. 💾
    
* `du -h [directory]`: Estimate file space usage. 📊
    
* `mount`: Show mounted filesystems. 🏔️
    
* `umount [mount_point]`: Unmount filesystem. 🗻
    

## Package Management:

**Debian/Ubuntu:**

* `apt-get`: Package Tool. 📦🔧
    
* `dpkg`: Package manager for .deb. 📦📦
    

**Red Hat/CentOS/Fedora:**

* `yum`: Package manager. 📦🔧
    
* `rpm`: Package manager for .rpm. 📦📦
    

**Process Monitoring:**

* `ps`: Display running processes. 🔄
    
* `top`: Monitor processes. 📈
    

**System Shutdown/Reboot:**

* `shutdown [options] [time]`: Shut down or reboot. 🚫🔄
    
* `reboot`: Reboot immediately. 🔄
    

**Help:**

* `man [command]`: Display manual. ℹ️
    
* `--help or -h`: Get help. ℹ️
    

# **Git & GitHub Commands Cheat Sheet** 🐙

### **Basic Git Commands** 🚀

* `git init`: Initialize Git repo.
    
* `git clone <repository_url>`: Clone remote repo.
    
* `git status`: Check repo status.
    
* `git add <file(s)>`: Add changes to staging. 📝
    
* `git commit -m "Commit message"`: Commit with the message. 💬
    
* `git log`: View commit history. 📜
    
* `git diff`: View commit differences. 📊
    
* `git checkout -- <file(s)>`: Discard changes. 🔄
    
* `git reset HEAD <file(s)>`: Unstage changes. 🙅‍♂️
    
* `git revert <commit_hash>`: Revert a commit. ⏪
    
* `git reset --hard <commit_hash>`: Reset to commit. 🔙
    
* `git clean -n`: List untracked files to be removed. 🗑️
    
* `git cherry-pick <commit_hash>`: Apply a specific commit. 🍒
    
* `git rebase <branch_name>`: Reapply commits on another base. 🔄
    

### **Branch & Tag Operations** 🌿🏷️

* `git branch`: List/create/delete branches. 🌐
    
* `git checkout <branch_name>`: Switch branch. 🔄
    
* `git checkout -b <branch_name>`: Create & switch. 🌱
    
* `git merge <branch_name>`: Merge branch. 🤝
    
* `git branch -d <branch_name>`: Delete branch. ❌
    
* `git tag <tag_name>`: Create a lightweight tag. 🏷️
    
* `git tag -a <tag_name> -m "Tag message"`: Create annotated tag. 🏷️
    

### **Stashing & Remote** 📦🌐

* `git stash`: Temporarily save changes. 📦
    
* `git stash apply`: Apply last stash. 📦
    
* `git stash pop`: Apply & remove last stash. 📦
    
* `git stash list`: List stashed changes. 📦
    
* `git stash drop`: Discard last stash. 📦
    
* `git remote add <remote_name> <repository_url>`: Add remote repo. 🌐
    
* `git remote -v`: List remotes & URLs. 🌐
    
* `git push <remote_name> <branch_name>`: Push commits. ☁️
    
* `git fetch <remote_name>`: Fetch changes. 🔄
    
* `git pull <remote_name> <branch_name>`: Pull changes. 🔄
    

### **Advanced Git Actions** 🚀

* `git reflog`: View the history of references. 📜
    
* `git log --graph --oneline --all`: Visualize the commit-graph concisely. 📈
    
* `git rebase <branch_name>`: Reapply commits on another base. 🔄
    

### **Note:** 🚀

***This cheat sheet contains all the commands used and mentioned in the past 11 blogs. It's a comprehensive and helpful resource that combines essential Linux commands for efficient file management and system control with powerful Git and GitHub commands for version control and collaborative coding. 🐧🐙 Elevate your skills, streamline your workflow, and navigate the coding universe with confidence. 💻 Embrace these tools to become a coder 🌟!***