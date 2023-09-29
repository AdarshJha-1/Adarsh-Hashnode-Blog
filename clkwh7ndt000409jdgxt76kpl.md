---
title: ""Day 4 DevOps Challenge -  Exploring Basic Linux Shell Scripting" 🚀💻📝"
datePublished: Fri Aug 04 2023 11:02:00 GMT+0000 (Coordinated Universal Time)
cuid: clkwh7ndt000409jdgxt76kpl
slug: day-4-devops-challenge-exploring-basic-linux-shell-scripting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691146780333/2cbe34d7-2b84-4b84-a9a0-825ee52120b8.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691146908995/c1456c3e-4854-46c2-ac95-2b4bb1c88189.webp
tags: software-development, linux, devops, shell-script, 90daysofdevops

---

## What is a Shell? 🐚

A shell is a friendly interface between you and your computer's operating system. It's like a virtual assistant that understands your text-based commands and helps you interact with the system. You can think of it as a way to talk to your computer using everyday language.

## What is Linux Shell Scripting? 🚀💻

Linux Shell Scripting is a way of automating tasks by writing a series of commands in a script file. It's like giving your virtual assistant a list of instructions to follow automatically. Instead of typing each command one by one, you can write them all in a script and run it. The shell reads the script and executes all the commands for you, saving time and effort.

## 📝 Getting Started with Shell Scripting for DevOps! 😎

Hello there, fellow noobs! 😄 If you're new to the world of DevOps and feeling a bit overwhelmed by all the jargon and technical terms, fear not! In this blog, we'll break down the basics of Shell Scripting and make it easy-peasy for you to understand. 🚀

## What is Shell Scripting for DevOps? 🚀💻🧙‍♂️

Shell Scripting is like having a superpower for automating tasks in the DevOps world. 🧙‍♂️ It's a way of writing simple scripts (sets of instructions) that can be executed in the command-line interface of your computer. These scripts help developers and system administrators perform repetitive tasks efficiently, saving time and effort.

**Example:**

***Let's say you want to automate the process of deploying a new version of your software. With Shell Scripting, you can write a script to handle all the necessary steps, such as pulling the latest code from the repository, building it, and deploying it on the server.***

## What is #!/bin/bash? Can we write #!/bin/sh as well? 🤔💭🔍

When you see "#!/bin/bash" at the top of a shell script, it means that the script should be interpreted and executed using the "bash" shell. Bash (Bourne Again SHell) is a popular shell with powerful features. But yes, you can use "#!/bin/sh" instead, which refers to the default shell on many systems. It might not have all the fancy features of bash, but it's more portable across different platforms.

## Writing a Shell Script to complete the #90DaysOfDevOps challenge: 🚀💻📝

Let's get our motivation game strong! Here's a simple script to print a commitment message for the #90DaysOfDevOps challenge:

```bash
#!/bin/bash

echo "I will complete #90DaysOfDevOps challenge"
```

  
To use this script, follow these simple steps:

1. Save the script in a file, for example, name it "[motivation.sh](http://motivation.sh)".
    
2. Make the script executable by running the command: `chmod +x` [`motivation.sh`](http://motivation.sh).
    
3. Run the script using the command: `./`[`motivation.sh`](http://motivation.sh).
    
4. The script will display the commitment message! 🎉
    

## Taking User Input and Using Arguments in Shell Scripting: 📥🔢📝

Shell scripts can also interact with users and accept input from them. You can use the `read` command to take input from the user during script execution.

Here's an example:

```bash
#!/bin/bash

# Taking user input
echo "What's your name?"
read name
echo "Hello, $name! Welcome to the world of DevOps."
```

When you run this script and provide your name as an argument, it will greet you and display the arguments you passed.

## Example of If-Else in Shell Scripting 🔄🔍🔀

Conditional statements like If-Else are super useful in Shell Scripting. They allow us to make decisions and execute different code blocks based on conditions.

```bash
#!/bin/bash

# Comparing two numbers
num1=10
num2=20

if [ $num1 -gt $num2 ]; then
    echo "$num1 is greater than $num2"
else
    echo "$num1 is not greater than $num2"
fi
```

In this example, we compare `num1` and `num2`, and the script will display the appropriate message based on the comparison result.

### In Conclusion: 🎯🌟🚀

Shell Scripting is a powerful tool in the DevOps toolbox that can save time and make life easier for developers and system administrators. With a bit of practice and creativity, you can automate various tasks and make your DevOps journey smoother than ever! So, keep scripting and exploring the world of DevOps! 🚀💻

Remember, even noobs can become experts with dedication and learning. Happy scripting! 🌟🎉 ( I am a noob too )