# Kubernetes Hands-On Guide - part 4

This repository contains hands-on exercises for key Kubernetes concepts in Lap 4. Each section contains YAML configuration files demonstrating their application in a Kubernetes cluster.

## 📂 Folder Structure
To maintain clarity and organization, the repository is structured as follows:

```
📦 k8s-lap4
 ┣ 📂 pv-pvc
 ┃ ┣ 📜 .yaml
 ┣ 📂 env-variables
 ┃ ┣ 📜 .yaml
 ┣ 📂 configmap
 ┃ ┣ 📜 .yaml
 ┣ 📂 secret-mysql
 ┃ ┣ 📜 .yaml
 ┣ 📂 init-container
 ┃ ┣ 📜 .yaml
 ┣ 📂 multi-container
 ┃ ┣ 📜 .yaml
 ┣ 📂 theoretical-questions
 ┃ ┣ 📜 .md
 ┗ 📜 README.md
```

Each directory contains:
- 📝 The corresponding **YAML configuration file**.

## Concepts Explained

### 1️⃣ Persistent Volume (PV) and Persistent Volume Claim (PVC)
A `PersistentVolume` (PV) is a storage resource in a Kubernetes cluster, while a `PersistentVolumeClaim` (PVC) is a request for storage by a user. They allow data persistence beyond the lifecycle of a pod.

📂 **Folder:** `pv/`

---

### 2️⃣ Environment Variables
Environment variables allow passing configuration settings into pods dynamically. This enables separating configuration from application code, making deployments more flexible.

📂 **Folder:** `env-variable/`

---

### 3️⃣ ConfigMap
A `ConfigMap` stores non-sensitive configuration data in key-value pairs and can be mounted as a volume or injected as environment variables in a pod.

📂 **Folder:** `configmap/`

---

### 4️⃣ Secret with MySQL
Kubernetes `Secret` objects securely store sensitive information, such as database credentials. This section demonstrates storing and using a MySQL password securely.

📂 **Folder:** `mysql-secret/`

---

### 5️⃣ Init Containers
`InitContainers` run before the main application container starts, performing setup tasks like waiting for a dependency to be ready or initializing configurations.

📂 **Folder:** `init-container/`

---

### 6️⃣ Multi-Container Pods
A pod can run multiple containers that share networking and storage. This setup is useful for sidecar patterns where one container assists another.

📂 **Folder:** `multi-container/`

---

### 7️⃣ Theoretical Questions
This section includes theoretical questions related to Lap 4 concepts, helping reinforce understanding of Kubernetes fundamentals.

📂 **Folder:** `theoretical-questions/`

