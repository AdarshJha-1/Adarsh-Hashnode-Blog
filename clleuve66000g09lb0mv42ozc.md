---
title: "🚀📅 Day 17 DevOps Challenge -🔮 Enchanted Django To-Do: AWS EC2 & Docker Magic for DevOps 🐍🐳"
seoTitle: "day-17-devops-challenge-enchanted-django-to-do-aws-ec2-docker-magic-fo"
seoDescription: "day-17-devops-challenge-enchanted-django-to-do-aws-ec2-docker-magic-for-devops"
datePublished: Thu Aug 17 2023 07:44:14 GMT+0000 (Coordinated Universal Time)
cuid: clleuve66000g09lb0mv42ozc
slug: day-17-devops-challenge-enchanted-django-to-do-aws-ec2-docker-magic-for-devops
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692258164441/ece6100e-041d-41c7-aab5-72bf652a43dc.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692258151908/ba79302e-7d2b-4f86-be69-49938b1b3918.png
tags: software-development, docker, django, web-development, devops

---

## 🐳 **Dockerfile Magic: Crafting Containers with Ease!** 🛠️

Hey, tech enthusiasts! 👋 If you've ever wondered how applications effortlessly glide across different environments, say hello to Docker – the sorcerer behind the scenes making this enchantment possible! 🪄✨

## **🏗️ Building Blocks: The Dockerfile Blueprint**

Think of a Dockerfile as your app's blueprint. It's the spellbook that guides Docker in crafting a magical container for your application. ⚙️ Imagine being the conductor of an orchestra, and Dockerfile is your symphony score, harmoniously bringing everything together.

### 🎭 Step by Step: Crafting the Dockerfile Choreography

1. **Foundation First**: Just like constructing a sturdy building, your Dockerfile begins by selecting a "base image." It's like choosing the canvas for your masterpiece. Whether it's a web server, database, or programming language – this is your starting point.
    
2. **Commands Unleashed**: Time to infuse life into your container! With Dockerfile, you direct Docker to execute commands – copying files, installing software, or running scripts. Consider it the dance moves that make your app groove. 💃🕺
    
3. **Dress for Success**: Your app needs its finest attire, right? Dockerfile lets you dress up your container by adding files, settings, and configurations. It's like choosing the perfect outfit to make your app dazzle. 💄👠
    
4. **Curtains Up**: The spotlight's on! When your container takes the stage, Dockerfile ensures the show runs smoothly. It's your backstage crew, ensuring your app's performance is flawless. 🎉🎬
    

### 🚀 Launching Your App: Countdown to Success 🚀

Think of Dockerfile as your recipe for success. Just like baking a cake, you follow the steps (commands) to mix ingredients (build the container) and create a delectable treat (run your app in a container). 🍰🍴

![What is Dockerfile and How to Create a Docker Image?](https://geekflare.com/wp-content/uploads/2019/07/dockerfile-697x270.png align="left")

Imagine you're creating a container for a website. Dockerfile brings the web server, site files, and essentials together. As the curtains rise, your website takes center stage! 🌐🎤

### ⚡ Dockerfile's Power: Making Complexity Simple ⚡

Dockerfile is your wand, transforming complex app setups into graceful performances. With a few lines of code, you encapsulate your app's universe and make it ready to shine on any platform! 🌟

The next time you dive into containers and Docker, remember that Dockerfile is your trusted guide – turning complexity into simplicity and giving your apps a standing ovation every time! 👏👏

## **🌟 Conjuring a To-Do App with Django on AWS EC2: Enchanting Development and Containerization 🐍🐳**

Before we start sculpting our To-Do app, ensure you have an AWS EC2 instance up and running.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692256528739/53b872da-2c2a-4d25-afc8-494f01db5649.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692256538825/eac89f1e-5ca0-4b5e-8177-78d7515960db.png align="center")

### 🔑 SSH Sorcery: Conquering Your EC2 Instance with Terminal Magic 🎩

With your AWS EC2 instance in place, it's time to work some SSH magic. Access your EC2 instance securely through the terminal:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692256704399/da7a9739-0a5c-4f77-bee5-8c241266b108.png align="center")

**🔄 Updating Your Kingdom: Unveiling the To-Do App 📜**

Once you're within the mystical realm of your EC2 instance, let's update it and install Docker and ensure everything is in order:

```bash
# Update the package repository
sudo apt update -y

# Install and Docker
sudo apt install docker -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692256837613/51409c42-0bef-49e9-b790-f9f95831af63.png align="center")

### 🚀 Code Snippet: Unveiling the To-Do App's Power 💡

For our To-Do app, we're going to summon a little bit of magic from a Git repository. You can fetch the incantation from your desired Git repository by replacing [`git_url`](https://github.com/LondheShubham153/django-todo-cicd.git) the below with your repository's URL:

```bash
# Clone the repository (replace git_url with your actual Git repository URL)
git clone https://github.com/LondheShubham153/django-todo-cicd.git
# Navigate to the project directory
cd your_project_directory
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692256866764/cdc0766b-46ba-4a5d-a304-b4717be205d1.png align="center")

### ⚙️ Adding Docker Magic: Containerizing the To-Do App 🐳

Containerization with Docker is our secret ingredient! It helps your app dance gracefully across different environments. To begin, let's conjure a Dockerfile. Imagine this Dockerfile as your app's personal magician, carrying out your wishes.

```bash
# Use the official Python 3 image as the base
FROM python:3

# Set the working directory within the container
WORKDIR /data

# Install Django version 3.2
RUN pip install django==3.2

# Copy all the files from the current directory into the container
COPY . .

# Run Django's database migrations
RUN python manage.py migrate

# Expose port 8000 for the Django app
EXPOSE 8000

# Command to run the Django app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

**🚀 Launching Your Enchanted To-Do App: Watch It Shine! 🌟**

With your Dockerfile ready, it's time to weave some Docker spells. Navigate to your app's directory, and use these commands:

```bash
# Build the Docker image
docker build -t todo-app .

# Run the Docker container
docker run -p 8000:8000 todo-app
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692256957708/dbbfa87a-4055-464d-a00b-3b1bd4b6cd7a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692257658386/00d9290c-10dc-4a79-85b9-2bac2decca24.png align="center")

### 🔍 Verifying the Enchantment: Witness Your To-Do App's Splendor 💼

Open your preferred web browser and journey to [`http://your-ec2-instance-ip:8000`](http://your-ec2-instance-ip:8000). Behold the wondrous power of your To-Do app, now gracing the AWS realm within the enchanting walls of a Docker container!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692257701886/d07d3016-a962-42db-a28d-3d921c795b68.png align="center")

### 🌐 Sharing the Enchantment: Pushing to the Docker Realm 🏰

Want to share your To-Do app with others? Let's push it to Docker Hub! First, log in to your Docker Hub account:

```bash
docker login
```

**Then, tag and push your image:**

```bash
docker tag todo-app:latest your-dockerhub-username/todo-app:latest
docker push your-dockerhub-username/todo-app:latest
```

**🎉 Wrapping Up: Applause for Your Enchanted To-Do App! 👏**

Congratulations, you've successfully conjured a To-Do app using Django and added an extra dash of magic with Docker. You're now ready to showcase your creation to the world, thanks to the power of containerization.

Stay curious, keep coding, and remember – there's no limit to the wonders you can create in the realm of tech. Until our next adventure, happy coding! 🧙‍♂️💻🌌