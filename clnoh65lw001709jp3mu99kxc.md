---
title: "🚀📅 Day 61 DevOps Challenge - Mastering ConfigMaps and Secrets in Kubernetes🔒🔑🛡️"
datePublished: Fri Oct 13 2023 10:37:48 GMT+0000 (Coordinated Universal Time)
cuid: clnoh65lw001709jp3mu99kxc
slug: day-61-devops-challenge-mastering-configmaps-and-secrets-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697193419417/64935d70-01e5-4719-8229-99b85222a773.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1697193461191/15f69f49-b093-4bdb-9220-1722c3ccef84.png
tags: web-development, developer, devops, hashnode, 90daysofdevops

---

Congratulations! In our previous Kubernetes journey, we delved into Namespaces and Services, fortifying our understanding of organizing and connecting different components within a Kubernetes cluster. Today, we'll embark on a new adventure exploring ConfigMaps and Secrets, essential tools for managing configuration data and sensitive information within Kubernetes. Let's dive right in and unravel the magic of ConfigMaps and Secrets! 💪💻🚀

## **ConfigMaps and Secrets in Kubernetes 🔒🔑🛡️**

ConfigMaps and Secrets are Kubernetes objects used to store configuration data and secrets, respectively.

* **ConfigMaps 📄⚙️** are used to store non-sensitive configuration data, such as database connection strings, application settings, and environment variables. ConfigMaps can be mounted into containers as environment variables, command-line arguments, or files.
    
* **Secrets 🤫🔐** are used to store sensitive data, such as passwords, API keys, and certificates. Secrets are encrypted at rest and in transit and can be accessed by Pods and other Kubernetes objects using a variety of methods.
    

ConfigMaps and Secrets are both stored as key-value pairs, but Secrets are encrypted by default. This means that Secrets should be used for storing any data that needs to be kept confidential, such as passwords and API keys. ConfigMaps can be used for storing any non-sensitive data that needs to be accessed by multiple containers or Pods.

Here are some examples of how ConfigMaps and Secrets can be used:

* **ConfigMaps 📄⚙️:**
    
    * Storing database connection strings 🛢️
        
    * Storing application settings such as logging levels and cache sizes ⚙️
        
    * Storing environment variables such as the port number that an application should listen on 🖥️
        
* **Secrets 🤫🔐:**
    
    * Storing passwords for databases and other applications 🔒
        
    * Storing API keys for cloud services ☁️
        
    * Storing certificates for TLS/SSL encryption 🛡️
        

ConfigMaps and Secrets are a powerful way to manage configuration data and secrets in Kubernetes. By using ConfigMaps and Secrets, you can decouple your applications from their configuration and environment, making them more portable and easier to manage.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697190461597/54f6dfb1-28cf-44b3-81f8-3fb44222f6f2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697190796803/97a8175c-cf21-4335-aab9-1adaaa044afd.png align="center")

# **Today's Tasks**

### **Task 1: ConfigMap Mastery**

In this task, we'll focus on mastering ConfigMaps to streamline configuration management within Kubernetes.

1. **Create a ConfigMap for your Deployment**:
    

* Utilize either a file or the command line to craft a ConfigMap tailored to your deployment's needs.
    
* let's create a file named `sample.conf` like this:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697191296461/c3ced821-4592-4810-9ab0-1b8e79c26357.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697191306495/6a5a3510-4e23-4603-8556-cc4187c83c38.png align="center")
    
* To create a ConfigMap for your Deployment using the `kubectl` command, you'll use the `create configmap` command. Here's a basic example:
    
    ```apache
    kubectl create configmap my-config --from-file=path/to/config/file -n <namespace-name>
    ```
    
* Replace `<namespace-name>` with the actual name of the namespace where you want to create the ConfigMap. In this example, we're creating a ConfigMap named `my-config` with the configuration data in a file, you can use the `--from-file` option to create the ConfigMap from a file:
    
* Replace `path/to/config/file` with the actual path to your configuration file.
    
    Make sure to adjust the ConfigMap name and data according to your specific use case and requirements.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697191498808/df66da4e-656a-4362-a6f4-16d261281322.png align="center")
    

1. **Integrate ConfigMap into the Deployment**:
    
    * Update your `deployment.yml` file to incorporate the ConfigMap, allowing your deployment to access the requisite configurations.
        
        ```yaml
        apiVersion: apps/v1
        kind: Deployment
        metadata:
          name: ubuntu-deployment
          labels:
            app: ubuntu
        spec:
          replicas: 1
          selector:
            matchLabels:
              app: ubuntu
          template:
            metadata:
              labels:
                app: ubuntu
            spec:
              containers:
              - name: ubuntucontainer
                image: ubuntu
                volumeMounts:
                - name: testconfigmap
                  mountPath: "/tmp/config"
              volumes:
              - name: testconfigmap
                configMap:
                  name: my-config
                  items:
                  - key: sample.conf
                    path: sample.conf
        ```
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697192570498/809aa810-9fe0-4e01-b2a8-9b4a2564695f.png align="center")
    
2. **Apply Deployment Changes**:
    
    * Execute the command `kubectl apply -f deployment.yml` to apply the updated deployment configuration.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697192881213/d872b4b5-9761-4360-ac8f-44f487da03e7.png align="center")
        
3. **Verification**:
    
    * Validate the successful creation of the ConfigMap by inspecting the status of ConfigMaps in your designated Namespace.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697191505708/eb4ff498-576d-49f1-88cb-b21b8ee15057.png align="center")
        
    * tomorrow we will see how to create **secrets**
        

Stay tuned for the journey ahead, where we'll continue to unravel the secrets of Kubernetes, enhancing our mastery over its diverse features and functionalities. Happy Kubernetes sailing! 🛡️🔑🚀