---
title: "🚀📅 Day 58 DevOps Challenge - 🚀 Launching your Kubernetes Cluster with Deployment"
seoDescription: "day-58-devops-challenge-launching-your-kubernetes-cluster-with-deployment"
datePublished: Sun Oct 08 2023 05:48:44 GMT+0000 (Coordinated Universal Time)
cuid: clnh1n5ci000008ie6z3gd6gg
slug: day-58-devops-challenge-launching-your-kubernetes-cluster-with-deployment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696743968897/64f70cf4-1abf-41e2-959a-290035a6f619.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696744013183/df31f1c5-9b27-4736-bb70-b1763bbe3bcd.png
tags: web-development, kubernetes, devops, 2articles1week, 90daysofdevops

---

In the exciting world of Kubernetes (K8s), one of the fundamental concepts you'll encounter is Deployment. 🛠️ But what exactly is a Deployment in K8s?

![Kubernetes Deployment Tutorial For Beginners](https://imgs.search.brave.com/IBn5QnzF8L2-IgVUySxgt5u845DPJ43BIgzCgcmXcpc/rs:fit:860:0:0/g:ce/aHR0cHM6Ly9kZXZv/cHNjdWJlLmNvbS93/cC1jb250ZW50L3Vw/bG9hZHMvMjAxOC8x/MS9LdWJlcm5ldGVz/LURlcGxveW1lbnQt/VHV0b3JpYWwtRm9y/LUJlZ2lubmVycy0x/MTYweDM4NS5wbmc align="left")

## **Understanding Deployment in K8s**

A Deployment in Kubernetes provides a robust configuration for managing updates for Pods and ReplicaSets. It allows you to define a desired state, and the Deployment Controller ensures that the actual state of your application aligns with this desired state at a controlled pace. This controlled rate of change helps in maintaining stability during updates and scaling.

![07751442 deployment](https://imgs.search.brave.com/Ns-1ADXGRtweS62s-fxrXB_w4g9s-JUW-jL6QQs6jnE/rs:fit:860:0:0/g:ce/aHR0cHM6Ly9zdG9y/YWdlLmdvb2dsZWFw/aXMuY29tL2Nkbi50/aGVuZXdzdGFjay5p/by9tZWRpYS8yMDE3/LzExLzA3NzUxNDQy/LWRlcGxveW1lbnQu/cG5n align="left")

You can use Deployments to achieve various objectives, such as creating new replicas for scaling your application or replacing existing Deployments and adopting all their resources with new ones. The flexibility of Deployments is a powerful tool in managing your applications effectively. 🔧

## **Today's Task**

Today, let's keep it simple yet impactful with a specific task.

For performing these tasks, ensure that you have Kubernetes/minikube installed on your local machine. Alternatively, you can use a cloud-based virtual machine such as an EC2 instance. If you haven't set up Kubernetes/minikube yet, you can refer to my previous blog 📖: [Install Minikube on your local machine or AWS EC2 instance](https://adarshdevops.hashnode.dev/day-57-devops-challenge-launching-your-first-kubernetes-cluster-with-nginx-a-minikube-adventure#heading-installing-minikube-on-ubuntu) 🌟🛠️

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696741600602/74e012ab-7b39-48f8-b32d-e73ee29b2dea.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696741621187/257b26a3-24df-42cf-afa4-ae3ad6e3b8e4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696741632737/199a8e2c-5d0a-46fd-965d-7f89efd84fb3.png align="center")

## **Task-1: Create a Sample Todo-App Deployment with "Auto-healing" and "Auto-Scaling" Features**

Your mission is to create a Deployment file that deploys a sample todo-app on your Kubernetes cluster using the "Auto-healing" and "Auto-Scaling" features.

### **Steps to Accomplish the Task:**

1. **Create a Deployment File:** On your EC2 instance where you've set up minikube, you'll need to create a file named `deployment.yaml`. This file will define the desired state of your cluster.
    
    Below is the sample deployment configuration. You can copy this and paste it into your `deployment.yaml` file.
    
    ```yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: nginx-deployment
      labels:
        app: nginx
    spec:
      replicas: 3
      selector:
        matchLabels:
          app: nginx
      template:
        metadata:
          labels:
            app: nginx
        spec:
          containers:
          - name: nginx
            image: nginx:1.14.2
            ports:
            - containerPort: 80
    ```
    
    > **Note: Don't worry about memorizing every detail of the file configuration (e.g., pod.yml or deployment.yml). You can simply refer to provided examples and modify them according to your specific needs.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696742484031/935b63cd-b439-4902-b408-9dc8ecc411b5.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696741733250/f6244f12-7105-4dbe-88e7-6d526a18a903.png align="center")
    
2. **Apply the Deployment:** Use the `kubectl apply` command to apply the Deployment configuration to your K8s (minikube) cluster. The command will look like this:
    
    ```apache
    kubectl apply -f deployment.yaml
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696742785508/0da6c4b1-8515-4558-93bd-e0e61558da9c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696742815750/375adc0a-c20a-469d-a06b-fb995039e99c.png align="center")

This simple yet impactful task will not only enhance your understanding of Deployments but also add another valuable project to your resume. Let's get coding and make your resume shine! 🌟

## **Closing Thoughts**

Thanks for reading my learning journey! I appreciate your time and dedication. If you find any mistakes or have any feedback, feel free to drop a comment. Your engagement means a lot! 😊 Don't forget to like and share this content to spread the knowledge. Let's connect on social media:

* **LinkedIn:** [Adarsh Jha 🧑‍💻](https://www.linkedin.com/in/adarsh2005/)
    
* **Twitter:** [**Adarsh Jha**](https://twitter.com/adarshjha__1)
    
* **Instagram:** [**𝐀𝐝𝐚𝐫𝐬𝐡**](https://www.instagram.com/adarshjha__1/)
    
* **GitHub:** [AdarshJha-1](https://github.com/AdarshJha-1)
    
* **Hashnode:** [AdarshJha](https://hashnode.com/@AdarshJha)
    
* **Hashnode Blogs:** [AdarshJha-Blogs](https://adarshdevops.hashnode.dev/)
    

Happy learning and coding! Keep exploring the fascinating world of Kubernetes and beyond. 💡