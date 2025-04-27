# Kubernetes Hands-On Guide - part 5

This repository contains hands-on exercises for key Kubernetes concepts in Lap 5. Each section contains YAML configuration files and/or commands demonstrating their application in a Kubernetes cluster.

## 📂 Folder Structure
To maintain clarity and organization, the repository is structured as follows:

📦 k8s-lap5
 ┣ 📂 etcd
 ┃ ┣ 📜 shell.txt
 ┣ 📂 ingress
 ┃ ┣ 📜 ingress.yaml
 ┃ ┣ 📜 commands.txt
 ┣ 📂 gateway
 ┃ ┣ 📜 Gateway-GatewayClass-httproute-.yaml
 ┃ ┣ 📜 shell.txt
 ┣ 📂 hpa
 ┃ ┣ 📜 hpa.yaml
 ┃ ┣ 📜 shell.txt
 ┣ 📂 metrics-server-vpa
 ┃ ┣ 📜 install matric server.txt
 ┃ ┗ 📜 vpa-installation.txt
 ┃ ┗ 📜 VPA-resource.yaml
 ┗ 📜 README.md



Each directory contains:
- 📝 The corresponding **YAML configuration file(s) or script(s)**.
- 📄 Potential **text files** with commands or instructions.

## Concepts Explained

### 1️⃣ Exploring `etcd`
`etcd` is a distributed key-value store that serves as Kubernetes' backing store for all cluster data. Understanding how to interact with and manage `etcd` is crucial for cluster operations.

📂 **Folder:** `etcd/`

- **`shell.txt`**: Contains shell commands for interacting with `etcd`.

---

### 2️⃣ Working with Ingress
An `Ingress` exposes HTTP and HTTPS routes from outside the cluster to services within the cluster. It acts as a traffic controller.

📂 **Folder:** `ingress/`

- **`ingress.yaml`**: A basic Ingress configuration demonstrating how to route external traffic to a service.
- **`commands.txt`**: Contains `kubectl` commands related to deploying and inspecting the Ingress.

---

### 3️⃣ Exploring Gateway API
The Gateway API is a more expressive and extensible evolution of the Ingress API, providing richer traffic routing capabilities.

📂 **Folder:** `gateway/`

- **`Gateway-GatewayClass-httproute-.yaml`**: Contains the YAML definitions for `GatewayClass`, `Gateway`, and `HTTPRoute` resources.
- **`shell.txt`**: Contains shell commands for deploying and interacting with the Gateway API resources.

---

### 4️⃣ Horizontal Pod Autoscaling (HPA)
`HorizontalPodAutoscaler` automatically scales the number of pod replicas in a deployment, statefulset, or replicaset based on observed CPU utilization or custom metrics.

📂 **Folder:** `hpa/`

- **`hpa.yaml`**: Configuration for an HPA that scales an application based on CPU utilization.
- **`shell.txt`**: Contains `kubectl` commands for deploying and observing the HPA.

---

### 5️⃣ Monitoring with Metrics Server & Vertical Pod Autoscaling (VPA)
Metrics Server collects resource consumption metrics from nodes and pods, while Vertical Pod Autoscaler automatically adjusts the CPU and memory requests/limits of pods to optimize resource utilization.

📂 **Folder:** `metrics-server-vpa/`

- **`install matric server.txt`**: Contains commands to install the Metrics Server.
- **`vpa-installation.txt`**: Contains commands related to installing the Vertical Pod Autoscaler.
- **`VPA-resource.yaml`**: Configuration for a VPA that automatically adjusts the resources of a deployment.
