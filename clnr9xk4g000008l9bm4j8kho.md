---
title: "🚀📅 Day 62 DevOps Challenge - Managing Persistent Volumes in Your Deployment 💥"
datePublished: Sun Oct 15 2023 09:38:28 GMT+0000 (Coordinated Universal Time)
cuid: clnr9xk4g000008l9bm4j8kho
slug: day-62-devops-challenge-managing-persistent-volumes-in-your-deployment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697362607469/ee36788c-ea1f-4a7a-96bd-f09051660db3.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1697362685800/8a963ae3-9ac4-41db-b27b-b19670dc24cc.png
tags: aws, web-development, kubernetes, devops, 90daysofdevops

---

Today, we're diving into managing Persistent Volumes (PVs) in Kubernetes, an essential aspect of efficient storage management

## **Understanding Persistent Volumes in Kubernetes 📚**

Persistent Volumes (PVs) in Kubernetes are fundamental components that facilitate persistent storage management within a Kubernetes cluster. They represent a crucial part of the Kubernetes architecture, ensuring data persistence and availability for applications that require storage.

## **What is a Persistent Volume (PV)? 💾**

A **Persistent Volume (PV)** is essentially a unit of storage provisioned within the Kubernetes cluster by an administrator. It can be seen as an abstraction layer that separates the storage provision and management from the applications that utilize it. The PV abstracts the underlying storage details, providing a consistent and persistent storage interface to the applications.

## **Requesting Storage with Persistent Volume Claims (PVCs) 🗂️**

When an application requires storage, a user initiates a request for storage by creating a **Persistent Volume Claim (PVC)**. The PVC is a declarative request specifying the desired storage requirements, such as capacity, access modes, and other parameters. This request is sent to the Kubernetes API server.

The PVC references a specific PV that matches its criteria in terms of capacity, access modes, and other requirements. The Kubernetes control plane then binds the PVC to the appropriate PV, establishing a connection between the application and the persistent storage.

![](https://imgs.search.brave.com/csmnCIJADMBty0ZGmq3trJ7asGaDkx3JArSCFfVOG-k/rs:fit:860:0:0/g:ce/aHR0cHM6Ly9waG9l/bml4bmFwLmNvbS9r/Yi93cC1jb250ZW50/L3VwbG9hZHMvMjAy/MS8wNC9ncmFwaGlj/LW9mLXBlcnNpc3Rl/bnQtdm9sdW1lLWJv/bmQucG5n align="left")

## **Utilizing Persistent Storage 🚀**

Once the PVC is bound to a PV, the application can utilize the persistent storage for its data needs. The PV, which is bound to a specific node in the cluster, ensures that the application has access to the requested storage.

## **Official Documentation 📖**

It's important to follow the official Kubernetes documentation on Persistent Volumes to understand the best practices, configuration options, and how to effectively manage and utilize persistent storage within a Kubernetes cluster. This documentation provides insights into how to provision, configure, and manage PVs and PVCs to optimize storage usage for applications running in a Kubernetes environment.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697360136655/b3e241aa-9eca-44a1-b789-75c9b0d9b572.png align="center")

## **Task 1: Adding a Persistent Volume to the Deployment**

1. **Create a Persistent Volume (PV) using a file on your node** (pv.yml):
    

```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-nginx-web
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  hostPath:
    path: "/tmp/data" # Replace with your host path
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697360209577/4f63255d-a69d-4be7-9e90-684acd3b3172.png align="center")

1. **Create a Persistent Volume Claim (PVC) that references the Persistent Volume** (pvc.yml):
    

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-nginx-web
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 500Mi
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697360314292/e1431c53-576a-4398-8f69-f3aa880340da.png align="center")

1. **Update your deployment.yml file to include the Persistent Volume Claim**:
    

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-web-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx-web
  template:
    metadata:
      labels:
        app: nginx-web
    spec:
      containers:
        - name: nginx-web-container
          image: nginx
          ports:
            - containerPort: 80  
          volumeMounts:
            - name: nginx-web-data
              mountPath: /app
      volumes:
        - name: nginx-web-data
          persistentVolumeClaim:
            claimName: pvc-nginx-web
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697360532502/e2d6fd9a-ba0a-41c6-8066-ac2ffa4f0b49.png align="center")

1. **Apply the configuration files**:
    

```apache
kubectl apply -f pv.yml
kubectl apply -f pvc.yml
kubectl apply -f deployment.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697360636056/7d7e88b8-1895-41c3-a282-018369e4f742.png align="center")

1. **Verify the Persistent Volume and Deployment**:
    

```apache
kubectl get pods
kubectl get pv
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697360679980/2102b967-bd5c-4a1c-aa9b-d07e6b0f1047.png align="center")

## **Task 2: Accessing data in the Persistent Volume**

1. **Connect to a Pod in your Deployment**:
    

```apache
kubectl exec -it <pod_name> -- /bin/bash
```

Replace `<pod_name>` with the actual Pod name in your deployment.

1. **Verify access to the Persistent Volume data from within the Pod**:
    

Once inside the Pod, navigate to the mount path (e.g., `/path/to/mount`) and verify that you can access the data stored in the Persistent Volume.