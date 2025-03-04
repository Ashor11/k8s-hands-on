Kubernetes Hands-On Guide

This repository contains hands-on exercises for key Kubernetes concepts. Each section contains YAML configuration files along with screenshots demonstrating their application in a Kubernetes cluster.

Folder Structure

To maintain clarity and organization, the repository is structured as follows:

📦 k8s-hands-on-guide
 ┣ 📂 limit-range
 ┃ ┣ 📜 limit-range.yaml
 ┃ ┣ 📷 limit-range-screenshot.png
 ┣ 📂 limits-requests
 ┃ ┣ 📜 limits-requests.yaml
 ┃ ┣ 📷 limits-requests-screenshot.png
 ┣ 📂 node-affinity
 ┃ ┣ 📜 node-affinity.yaml
 ┃ ┣ 📷 node-affinity-screenshot.png
 ┣ 📂 node-selector
 ┃ ┣ 📜 node-selector.yaml
 ┃ ┣ 📷 node-selector-screenshot.png
 ┣ 📂 resource-quota
 ┃ ┣ 📜 resource-quota.yaml
 ┃ ┣ 📷 resource-quota-screenshot.png
 ┣ 📂 taints-tolerations
 ┃ ┣ 📜 taints-tolerations.yaml
 ┃ ┣ 📷 taints-tolerations-screenshot.png
 ┣ 📂 namespaces
 ┃ ┣ 📜 namespace.yaml
 ┃ ┣ 📷 namespace-screenshot.png
 ┣ 📂 java-app
 ┃ ┣ 📜 java-app.yaml
 ┃ ┣ 📷 java-app-screenshot.png
 ┗ 📜 README.md

Each directory contains:

The corresponding YAML configuration file.

A screenshot showcasing the execution and application in Kubernetes.

1. Default Limit Range

A LimitRange is a policy that enforces minimum and maximum compute resources within a namespace. This ensures efficient resource allocation and prevents excessive consumption by any single pod.

(YAML file and screenshot included in limit-range/ folder)

2. Limits and Requests

Kubernetes allows defining resource requests and limits to ensure fair distribution of CPU and memory among pods. Requests guarantee minimum resources, while limits prevent overconsumption.

(YAML file and screenshot included in limits-requests/ folder)

3. Node Affinity

Node affinity enables scheduling pods on specific nodes based on labels. This is useful for ensuring workloads run on suitable hardware or within designated environments.

(YAML file and screenshot included in node-affinity/ folder)

4. Node Selector

The nodeSelector field is a simple way to assign pods to specific nodes based on key-value labels. This ensures that workloads are placed on the appropriate infrastructure.

(YAML file and screenshot included in node-selector/ folder)

5. Resource Quota

A ResourceQuota restricts the total amount of CPU, memory, and other resources a namespace can consume. This helps prevent excessive usage by a single namespace.

(YAML file and screenshot included in resource-quota/ folder)

6. Taints and Tolerations

Taints allow nodes to repel pods unless the pods have matching tolerations. This is useful for reserving nodes for specific workloads or preventing certain pods from being scheduled on specific nodes.

(YAML file and screenshot included in taints-tolerations/ folder)

7. Namespaces

Namespaces help logically separate resources within a cluster. They are useful for organizing workloads, enforcing policies, and managing multi-tenant environments.

(YAML file and screenshot included in namespaces/ folder)

8. Running a Java App from Docker Hub in a Pod

This example demonstrates how to deploy a Java application using an image from Docker Hub within a Kubernetes pod. The pod runs a Java application packaged as a JAR file.

(YAML file and screenshot included in java-app/ folder)

