---
title: "🚀📅 Day 59 DevOps Challenge - Working with Namespaces and Services in Kubernetes 🚀"
datePublished: Mon Oct 09 2023 09:43:31 GMT+0000 (Coordinated Universal Time)
cuid: clnipgxw0000009i84tss519u
slug: day-59-devops-challenge-working-with-namespaces-and-services-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696844480193/e441a3cd-efe5-4c4b-bf8a-cb69c1c66446.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696844601477/74404c2f-9b8d-46b9-9dd1-32ffa5ad4f40.png
tags: web-development, kubernetes, devops, 2articles1week, 90daysofdevops

---

Congratulations on your recent update to the Deployment in Kubernetes! Today, we'll delve into two fundamental concepts in Kubernetes: Namespaces and Services. Understanding and effectively utilizing Namespaces and Services is crucial in managing and deploying applications in a Kubernetes cluster.

# **Namespaces in Kubernetes 🏗️**

Namespaces in Kubernetes provide a way to create a logically isolated and segregated environment within a Kubernetes cluster. This isolation helps in organizing and managing resources effectively by preventing naming conflicts and providing scope-bound access and resource allocation.

Namespaces are especially beneficial in multi-tenant environments, where multiple teams or applications share the same Kubernetes cluster. Each Namespace operates as a separate virtual cluster, allowing you to:

1. **Isolate Resources**: Pods, Services, Deployments, and other resources in one Namespace are distinct from those in another Namespace, even if they have the same names.
    
2. **Control Access and Policies**: You can define access controls and policies specific to a Namespace, regulating who can access and modify the resources within that Namespace.
    
3. **Resource Quotas and Limits**: Set resource quotas and limits at the Namespace level, preventing any single Namespace from consuming excessive cluster resources.
    
4. **Simplified Resource Management**: Easily manage and view resources within a particular application or project by organizing them into dedicated Namespaces.
    

**Today, let's keep it simple yet impactful with a specific task.**

For performing these tasks, ensure that you have Kubernetes/minikube installed on your local machine. Alternatively, you can use a cloud-based virtual machine such as an EC2 instance. If you haven't set up Kubernetes/minikube yet, you can refer to my previous blog 📖: [**Install Minikube on your local machine or AWS EC2 instance**](https://adarshdevops.hashnode.dev/day-57-devops-challenge-launching-your-first-kubernetes-cluster-with-nginx-a-minikube-adventure#heading-installing-minikube-on-ubuntu) 🌟🛠️

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842149461/1733d585-3d40-459d-bc35-2fd0c1b1bbd8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842171757/397e1bbb-8575-453b-84da-4bb9a8f6551d.png align="center")

# **Task 1: Creating a Namespace for your Deployment 🛠️**

## **Step 1: Create a Namespace 🌐**

To create a Namespace, follow these steps:

1. **Create a YAML file**: Create a new YAML file, for example, `my-namespace.yaml`, and add the following content to it:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842225431/e045bb0a-4f3f-4d20-8abb-0e0eea181f4b.png align="center")
    

```apache
apiVersion: v1
kind: Namespace
metadata:
  name: <insert-namespace-name-here>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842293561/04e6a798-8386-4565-935d-0351e82e9ce7.png align="center")

Replace `<insert-namespace-name-here>` with your desired Namespace name.

1. **Run the Command via YAML**: Run the following command to create the Namespace using the YAML file:
    

```apache
kubectl create -f ./my-namespace.yaml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842367915/c94b8b4d-5a27-48ef-9124-2d7d6e01ba83.png align="center")

Alternatively, you can create the Namespace directly using the following command:

```apache
kubectl create namespace <insert-namespace-name-here>
```

Replace `<insert-namespace-name-here>` with your desired Namespace name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842413140/5bafb6a2-bb1d-472a-8157-861478366f09.png align="center")

Creating a Namespace using either method achieves the same result—creating an isolated environment within your Kubernetes cluster to organize and manage your resources effectively.

## **Step 2: Creating Resources in a Specified Namespace 🛠️**

In Kubernetes, you can create resources within a specific Namespace using either the `deployment.yaml` file or the `kubectl apply` command. Let's explore both methods:

### Method 1: Specifying Namespace in the deployment.yaml File 📝

1. **Open your** `deployment.yaml` file: Navigate to the `metadata` section and add the `namespace` field to specify the Namespace:
    

```apache
apiVersion: apps/v1
kind: Deployment
metadata:
  name: your-deployment
  namespace: <namespace-name>
  # ... other metadata fields
spec:
  # ... rest of the deployment configuration
```

Replace `<namespace-name>` with the desired Namespace name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842724588/d187f30e-a913-423c-9fdb-7eb579f2c6d0.png align="center")

1. **Apply the updated deployment**: Run the following command to apply the updated configuration and create the resources in the specified Namespace:
    

```apache
kubectl apply -f deployment.yaml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842780560/be69bae1-e813-4579-8174-e0e7202271e4.png align="center")

### Method 2: Using the kubectl apply Command with -n Flag 🚀

1. **Run the kubectl apply command**: Use the `kubectl apply` command along with the `-n` flag to specify the Namespace directly:
    

```apache
kubectl apply -f deployment.yaml -n <namespace-name>
```

Replace `<namespace-name>` with the desired Namespace name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842870346/0f2f3be9-e3d6-47c1-a08f-b9d77c2f363f.png align="center")

By using either of these methods, you ensure that your resources are created within the designated Namespace, organizing and isolating them for efficient management within your Kubernetes cluster.

Choose the method that suits your workflow and allows for seamless resource creation and management.

## **Step 3: Verifying the Namespace and Checking Resource Association 🧐**

After creating the Namespace and deploying resources within it, it's important to verify that the Namespace was successfully created and that the resources are associated with the intended Namespace. Let's go through the verification steps:

### Verify Namespace Creation

To confirm the creation of the Namespace, run the following command to list all the Namespaces in your Kubernetes cluster:

```apache
kubectl get namespaces
```

You should see the Namespace you created listed among the other Namespaces.

### Checking Resource Namespace Association

Next, let's check the association of the resources (e.g., Deployment) with the Namespace.

1. **List Deployments within the Namespace**: Run the following command to list all Deployments within the specified Namespace:
    

```apache
kubectl get deployments -n <namespace-name>
```

Replace `<namespace-name>` with the actual Namespace name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842910872/6d96d584-6137-43d8-9239-0946de478fb2.png align="center")

1. **List Pods within the Namespace**: Similarly, check the Pods associated with the Namespace using:
    

```apache
kubectl get pods -n <namespace-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696842944221/4b6b82f6-a22a-4f38-a61e-7c8e6f0991eb.png align="center")

This will provide information about Pods deployed in the specified Namespace.

By performing these checks, you can validate that the Namespace was created successfully, and the resources are correctly scoped within the designated Namespace. This ensures a well-organized and isolated environment for managing and deploying your applications in Kubernetes. 🌟🔍

# **Task 2: Understanding Services, Load Balancing, and Networking in Kubernetes 🌐**

In Kubernetes, Services, Load Balancing, and Networking are fundamental concepts that play a crucial role in ensuring seamless communication, availability, and scalability of applications. Let's delve into these concepts and gain a comprehensive understanding:

### **Understanding Kubernetes Services 🌐**

A Kubernetes Service is an abstraction that provides a consistent way to access a set of Pods. It ensures that your application remains accessible and reliable by abstracting away the underlying complexities of managing individual Pod IP addresses. Services help in decoupling the application from the infrastructure, allowing for easier scaling and maintenance.

### **Load Balancing with Kubernetes Services ⚖️**

Kubernetes Services automatically distributes incoming traffic to the appropriate Pods based on defined rules. This load balancing helps in distributing workloads efficiently and achieving high availability. Kubernetes supports various load balancing strategies, such as Round Robin, Source IP Affinity, and more, to ensure fair distribution of traffic.

### **Networking in Kubernetes 🌐**

Kubernetes manages networking through a range of abstractions, including Services, Pods, Ingress, and Network Policies. Understanding and configuring networking is vital for ensuring secure and reliable communication between components of your application. Networking in Kubernetes enables various features like inter-pod communication, external access, load balancing, and network segmentation.

#### **Task 2: Your Learning Assignment 📚**

Your task is to deep dive into the following aspects related to Services, Load Balancing, and Networking in Kubernetes:

1. **Kubernetes Services**: Read about different types of Kubernetes Services (ClusterIP, NodePort, LoadBalancer, and ExternalName) and understand when to use each type. 📖
    
2. **Load Balancing in Kubernetes**: Explore various load balancing strategies and how they can be configured for Kubernetes Services. Understand the importance of load balancing for maintaining application availability and reliability. ⚖️
    
3. **Networking Abstractions in Kubernetes**: Learn about various networking abstractions like Ingress, and Network Policies, and how they contribute to secure communication and network management within a Kubernetes cluster. 🛡️
    
4. **Best Practices**: Familiarize yourself with best practices for configuring Services, load balancing, and network policies to optimize your applications' performance, security, and reliability. 🚀
    

By mastering these concepts, you'll be better equipped to design, deploy, and manage your applications in Kubernetes with a focus on effective networking and load balancing. Happy learning! 🚀📖

## **Closing Thoughts**

Thanks for reading my learning journey! I appreciate your time and dedication. If you find any mistakes or have any feedback, feel free to drop a comment. Your engagement means a lot! 😊 Don't forget to like and share this content to spread the knowledge. Let's connect on social media:

* **LinkedIn:** [**Adarsh Jha 🧑‍💻**](https://www.linkedin.com/in/adarsh2005/)
    
* **Twitter:** [**Adarsh Jha**](https://twitter.com/adarshjha__1)
    
* **Instagram:** [**𝐀𝐝𝐚𝐫𝐬𝐡**](https://www.instagram.com/adarshjha__1/)
    
* **GitHub:** [**AdarshJha-1**](https://github.com/AdarshJha-1)
    
* **Hashnode:** [**AdarshJha**](https://hashnode.com/@AdarshJha)
    
* **Hashnode Blogs:** [**AdarshJha-Blogs**](https://adarshdevops.hashnode.dev/)
    

Happy learning and coding! Keep exploring the fascinating world of Kubernetes and beyond. 💡