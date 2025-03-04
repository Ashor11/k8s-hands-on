# Kubernetes Hands-On Guide

This repository contains hands-on exercises for key Kubernetes concepts. Each section contains YAML configuration files along with screenshots demonstrating their application in a Kubernetes cluster.

## 📂 Folder Structure
To maintain clarity and organization, the repository is structured as follows:

```
📦 k8s-hands-on-guide
 ┣ 📂 limit-range
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 limits-requests
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 node-affinity
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 node-selector
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 resource-quota
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 taints-tolerations
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 namespaces
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┣ 📂 java-app
 ┃ ┣ 📜 .yaml
 ┃ ┣ 📷 .png
 ┗ 📜 README.md
```

Each directory contains:
- 📝 The corresponding **YAML configuration file**.
- 📷 A **screenshot** showcasing the execution and application in Kubernetes.

##  Concepts Explained

### 1️⃣ Default Limit Range
A `LimitRange` is a policy that enforces minimum and maximum compute resources within a namespace. This ensures efficient resource allocation and prevents excessive consumption by any single pod.

📂 **Folder:** `limit-range/` *(YAML and screenshot included)*

---

### 2️⃣ Limits and Requests
Kubernetes allows defining resource requests and limits to ensure fair distribution of CPU and memory among pods. Requests guarantee minimum resources, while limits prevent overconsumption.

📂 **Folder:** `limits-requests/` *(YAML and screenshot included)*

---

### 3️⃣ Node Affinity
Node affinity enables scheduling pods on specific nodes based on labels. This is useful for ensuring workloads run on suitable hardware or within designated environments.

📂 **Folder:** `node-affinity/` *(YAML and screenshot included)*

---

### 4️⃣ Node Selector
The `nodeSelector` field is a simple way to assign pods to specific nodes based on key-value labels. This ensures that workloads are placed on the appropriate infrastructure.

📂 **Folder:** `node-selector/` *(YAML and screenshot included)*

---

### 5️⃣ Resource Quota
A `ResourceQuota` restricts the total amount of CPU, memory, and other resources a namespace can consume. This helps prevent excessive usage by a single namespace.

📂 **Folder:** `resource-quota/` *(YAML and screenshot included)*

---

### 6️⃣ Taints and Tolerations
Taints allow nodes to repel pods unless the pods have matching tolerations. This is useful for reserving nodes for specific workloads or preventing certain pods from being scheduled on specific nodes.

📂 **Folder:** `taints-tolerations/` *(YAML and screenshot included)*

---

### 7️⃣ Namespaces
Namespaces help logically separate resources within a cluster. They are useful for organizing workloads, enforcing policies, and managing multi-tenant environments.

📂 **Folder:** `namespaces/` *(YAML and screenshot included)*

---

### 8️⃣ Running a Java App from Docker Hub in a Pod
This example demonstrates how to deploy a Java application using an image from Docker Hub within a Kubernetes pod. The pod runs a Java application packaged as a JAR file.

📂 **Folder:** `java-app/` *(YAML and screenshot included)*

