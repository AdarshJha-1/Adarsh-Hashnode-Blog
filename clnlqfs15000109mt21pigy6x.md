---
title: "🚀📅 Day 60 DevOps Challenge - Working with Services in Kubernetes 🛠️"
datePublished: Wed Oct 11 2023 12:33:55 GMT+0000 (Coordinated Universal Time)
cuid: clnlqfs15000109mt21pigy6x
slug: day-60-devops-challenge-working-with-services-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697027432955/703bef5a-f1da-4bf5-868b-9cccadf3555f.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1697027615662/be2d1441-9064-4163-8249-74d64ee9386d.png
tags: web-development, kubernetes, hashnode, 2articles1week, 90daysofdevops

---

Congratulations on your progress in learning about Deployments in Kubernetes on Day-59! Today, we will dive into another essential aspect of Kubernetes: Services. Services are vital for providing stable network identities to Pods and abstracting away the complexities of Pod IP addresses. They enable Pods to receive traffic from other Pods, Services, and external clients efficiently.

## **Understanding Services in Kubernetes**

In Kubernetes, Services are objects that facilitate the communication between various parts of an application. They act as an intermediary, providing a stable network identity for Pods, which may come and go due to scaling, updates, or failures. Services abstract away the need for clients to know specific Pod IPs, making the overall architecture more resilient and easier to manage.

## **Task-1: Creating a Service for the NGINX Deployment**

Let's start by creating a Service for the NGINX Deployment.

### **Step 1: Create a Service Definition YAML file**

```apache
# nginx-service.yml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697025153547/82823978-d849-47be-8bc0-2ea20a5447f5.png align="center")

### **Step 2: Apply the Service Definition**

Apply the Service definition to your Kubernetes (minikube) cluster using the following command:

```apache
kubectl apply -f nginx-service.yml -n <namespace-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697025559816/88934f82-c2a7-4178-b6a7-1173b507d1fd.png align="center")

Replace `<namespace-name>` with the appropriate namespace for your environment.

### **Step 3: Verify the Service**

To check if a Kubernetes Service has been successfully created, you can use the `kubectl get services` command. This command lists all the services in the specified namespace.

```apache
kubectl get services -n <namespace-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697025588392/fa96d537-4bfc-4b4f-aa9e-e7f15f61f22e.png align="center")

Replace `<namespace-name>` with the namespace where you created the service. This command will display a table with information about all the services in that namespace, including the service name, type, cluster IP, external IP (if applicable), and ports.

If the service you created is listed in the output, it means the service has been successfully created in the Kubernetes cluster.

Verify that the Service is working by accessing the NGINX service using the Service's IP and Port within your Namespace. like this

```apache
# 1st 
minikube ssh
# 2nd
curl <CLUSTER-IP>  
# or
curl <CLUSTER-IP>:PORT
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697025732603/26254594-2a02-4ca2-a250-d858cb269d0a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697025745748/67264bfb-c238-4bc7-808a-dae18ede69b3.png align="center")

## **Task-2: Creating a ClusterIP Service for internal access**

Now, let's create a ClusterIP Service for accessing the NGINX service from within the cluster.

### **Step 1: Create a ClusterIP Service Definition YAML file**

```apache
# nginx-cluster-ip-service.yml
apiVersion: v1
kind: Service
metadata:
  name: nginx-cluster-ip
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: ClusterIP
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697026025153/f718697c-1923-4618-adf3-c02bc600c88b.png align="center")

### **Step 2: Apply the ClusterIP Service Definition**

Apply the ClusterIP Service definition to your Kubernetes (minikube) cluster using the following command:

```apache
kubectl apply -f nginx-cluster-ip-service.yml -n <namespace-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697026503579/e893dfc7-fb63-4a82-808d-1d8cd85468f2.png align="center")

Replace `<namespace-name>` with the appropriate namespace for your environment.

### **Step 3: Verify the ClusterIP Service**

Verify that the ClusterIP Service is working by accessing the NGINX service from another Pod in the cluster within your Namespace.

## **Task-3: Creating a LoadBalancer Service for external access**

Lastly, let's create a LoadBalancer Service for accessing the NGINX service from outside the cluster.

### **Step 1: Create a LoadBalancer Service Definition YAML file**

```apache
# nginx-load-balancer-service.yml
apiVersion: v1
kind: Service
metadata:
  name: nginx-load-balancer
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: LoadBalancer
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697026541584/605faeac-7e8a-4404-8e7a-edfc8463d130.png align="center")

### **Step 2: Apply the LoadBalancer Service Definition**

Apply the LoadBalancer Service definition to your Kubernetes (minikube) cluster using the following command:

```apache
kubectl apply -f nginx-load-balancer-service.yml -n <namespace-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697026579274/15762592-396e-49c3-b67a-7aaa074d7973.png align="center")

Replace `<namespace-name>` with the appropriate namespace for your environment.

### **Step 3: Verify the LoadBalancer Service**

Verify that the LoadBalancer Service is working by accessing the NGINX service from outside the cluster within your Namespace.

### To check the Kubernetes Services

To check if a Kubernetes Service has been successfully created, you can use the `kubectl get services` command. This command lists all the services in the specified namespace.

```apache
kubectl get services -n <namespace-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697026890585/73271a32-d361-4d13-b389-bfd105d13822.png align="center")

## **Conclusion**

Understanding and working with Services in Kubernetes is a crucial skill for managing applications effectively within a cluster. By following these tasks, you have gained hands-on experience in creating and using different types of Services for an NGINX application, allowing seamless communication between various components of your applications. Keep exploring and mastering Kubernetes to enhance your skills further! Happy learning! 🚀

## **Closing Thoughts**

Thanks for reading my learning journey! I appreciate your time and dedication. Today's Blog is not so very good :\[ but I tried my best I'm still learning all these things so please If you find any mistakes or have any feedback, feel free to drop a comment. Your engagement means a lot! 😊 Don't forget to like and share this content to spread the knowledge. Let's connect on social media:

* **LinkedIn:** [**Adarsh Jha 🧑‍💻**](https://www.linkedin.com/in/adarsh2005/)
    
* **Twitter:** [**Adarsh Jha**](https://twitter.com/adarshjha__1)
    
* **Instagram:** [**𝐀𝐝𝐚𝐫𝐬𝐡**](https://www.instagram.com/adarshjha__1/)
    
* **GitHub:** [**AdarshJha-1**](https://github.com/AdarshJha-1)
    
* **Hashnode:** [**AdarshJha**](https://hashnode.com/@AdarshJha)
    
* **Hashnode Blogs:** [**AdarshJha-Blogs**](https://adarshdevops.hashnode.dev/)
    

Happy learning and coding! Keep exploring the fascinating world of Kubernetes and beyond. 💡