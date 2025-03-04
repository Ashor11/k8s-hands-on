
# Kubernetes part 3 - Hands-On Guide

This repository contains hands-on exercises for key Kubernetes concepts in **Lap 3**. Each section includes YAML configuration files demonstrating their application in a Kubernetes cluster.

## 📂 Folder Structure
To maintain clarity and organization, the repository is structured as follows:

```
📦 lap3
 ┣ 📂 external-web-service
 ┃ ┣ 📜 .yaml
 ┣ 📂 internal-web-test
 ┃ ┣ 📜 .yaml
 ┣ 📂 daemonset
 ┃ ┣ 📜 .yaml
 ┣ 📂 theoretical-solutions
 ┃ ┣ 📜 solutions.md
 ┗ 📜 README.md
```

Each directory contains:
- 📝 The corresponding **YAML configuration file**.
- 📄 **Theoretical solutions** where applicable.

##  Concepts Explained

### 1 External Web Service (NodePort)
A `NodePort` service exposes an application externally by assigning a static port on each node in the cluster. This allows external users to access the application.

📂 **Folder:** `external-web-service/`

---

### 2 Internal Web Test (ClusterIP)
A `ClusterIP` service is used for internal communication between pods within a cluster. This is useful for microservices and backend applications that do not need external exposure.

📂 **Folder:** `internal-web-test/`

---

### 3 DaemonSet
A `DaemonSet` ensures that a specific pod runs on all (or some) nodes in the cluster. It is useful for logging, monitoring, and security applications that need to be present on every node.

📂 **Folder:** `daemonset/`

---

### 4 Theoretical Questions and Solutions
This section provides answers to theoretical Kubernetes questions related to service networking, resource management, and workload scheduling.

📂 **Folder:** `theoretical-solutions/`

