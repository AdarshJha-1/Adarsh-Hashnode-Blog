---
title: "Day 3 DevOps challenge - Mastering Basic Linux Commands: A Practical Guide"
seoTitle: "Linux-Command-Mastery-Practical-Guide"
seoDescription: "Explore widely-used Linux commands in this blog, mastering the basics for a practical understanding of terminal magic worldwide. 🚀🌍 #LinuxCommands"
datePublished: Fri Aug 04 2023 10:02:03 GMT+0000 (Coordinated Universal Time)
cuid: clkwf2jip000209mnb9flaa5c
slug: unleash-linux-power-terminal-magic
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691143023440/ebf351dd-9628-4135-a4fa-4f48ac05d323.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691143180726/ae9d95cc-862b-47b8-9a01-2fbde7fab7b4.png
tags: linux, command-line, devops, 90daysofdevops, shubhamlondhe

---

# 🐧🛠️ What Are Linux Commands? 🚀💻

🐧🔧 The term "**Linux command**" refers to the various commands that can be used in the Linux operating system's terminal (also known as the shell or command-line interface) to perform specific tasks, manage files, manipulate data, and control the system. 💻🛠️

Linux commands are usually typed in the terminal, and they follow a general syntax: `command [options] [arguments]`. The basic structure is as follows:

👉 `command`: The name of the Linux command you want to execute.

👉 `options`: Optional flags or switches that modify the behavior of the command.

👉 `arguments`: Input data or parameters required by the command. 📥

### 📄 To View What's Written in a File 🧐

***📄 View File Contents with*** `cat` ***Command 🐱***

With the `cat` command in Linux, you can easily display the contents of a file directly on the terminal. It's as simple as 🐱 and allows you to see what's inside at a glance!🚀 Let's assume we have a file named `example.txt` with the following content: ***"This is an example file. Hello, world!"***

To view the content of the `example.txt` file, you can use the `cat` command like this:

```basic
cat example.txt
```

**Output:**

```bash
This is an example file.
Hello, world!
```

### 🔒 **To Change the Access Permissions of Files**🔒

***🔐 Changing File Permissions with*** `chmod` ***Command 🛡️***

In Linux, the `chmod` command is used to change file permissions. It controls who can 👀 read(r), ✍️ write (w), and 🏃 execute(x) the file.

Let's say we have a file named `example.txt` Default permissions: `-rw-r--r--` (Owner can read and write, Group and Others can only read)

To give full control to the owner, group, and others (equivalent to `777`), you can use the `chmod` command as follows:

```bash
chmod 777 example.txt
```

Updated permissions: `-rwxrwxrwx` The permission `777` grants full read, write and execute access to the file for the owner (root), group, and other users.

### 🔍📜 To check which commands you have run till now💻:

You can use the `history` command to display a list of previously executed commands in the terminal.

```bash
history
```

### 🗑️📂 To remove a directory/folder in Linux 🐧💻:

1. **To remove an empty directory using** `rmdir`**:**
    
    ```bash
    rmdir directory_name
    ```
    
2. **To remove a directory and its contents recursively using** `rm`**:**
    
    ```bash
    rm -r directory_name
    ```
    
3. To remove a file using `rm:`
    
    ```bash
    rm filename.txt
    ```
    

### To create a 🍊fruits.txt file and to view👀 the content📝

1. To create the `fruits.txt` file:
    

```bash
echo -e "Apple\nBanana\nOrange\nGrapes" > fruits.txt
```

1. To view the content of the `fruits.txt` file, you can use `cat`:
    

```bash
cat fruits.txt
```

### Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

  
To add the content into a file named `devops.txt` with each item on a new line, you can use the following command:

```bash
echo -e "Apple\nMango\nBanana\nCherry\nKiwi\nOrange\nGuava" > devops.txt
```

This command uses the `echo` command with the `-e` option to enable interpretation of escape characters like `\n` (newline). It then redirects the output of `echo` to the `devops.txt` file, effectively creating the file with the specified content, with each item on a new line.

### 🍊 Show Top Three Fruits from the File 🍎

To show only the top three fruits from the file `devops.txt`, you can use the `head` command

```bash
head -n 3 devops.txt
```

### 🍉 Show the Bottom Three Fruits from the File 🍇

To show only the bottom three fruits from this file, you can use the following command

```bash
tail -n 3 devops.txt
```

### 🎨📝 Create Colors.txt and 📖 View the Content 🎨📝

To create a new file named `Colors.txt` and view its content, you can use the following commands:

1. To create the `Colors.txt` file:
    

```bash
echo -e "Red\nGreen\nBlue\nYellow\nOrange\nPurple\nPink" > Colors.txt
```

1. To view the content of the `Colors.txt` using `cat`:
    

```bash
cat Colors.txt
```

### 🔍📝 Finding Differences between fruits.txt and Colors.txt 🔍📝

To find the difference between the `fruits.txt` and `Colors.txt` files, you can use the `diff` command. The `diff` command compares two files line by line and shows the lines that are different. Here's how you can do it:

```bash
diff fruits.txt Colors.txt
```

***Mastering Linux commands unlocks endless possibilities! 🚀💻 From managing systems to manipulating data, these tools empower you to take full control. Embrace the command line and venture forth with confidence into the world of Linux! 🐧💪 Happy exploring! 🌟***