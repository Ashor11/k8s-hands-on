# Kubernetes Theoretical Questions

This section provides answers to theoretical Kubernetes questions related to **DaemonSets**, **static pods**, and **cluster configuration**.

## Questions

### 1️⃣ How many DaemonSets are created in the cluster in all namespaces?
To check the number of DaemonSets across all namespaces, use:
```sh
kubectl get daemonsets --all-namespaces
```

### 2️⃣ What DaemonSets exist in the `kube-system` namespace?
To list the DaemonSets running in the `kube-system` namespace, use:
```sh
kubectl get daemonsets -n kube-system
```

### 3️⃣ What is the image used by the pod deployed by the `kube-proxy` DaemonSet?
To check the container image used by `kube-proxy`, run:
```sh
kubectl get daemonset kube-proxy -n kube-system -o wide
```

### 4️⃣ How many static pods exist in this cluster in all namespaces?
Static pods are managed directly by `kubelet`, not the API server. To list them, use:
```sh
ls /etc/kubernetes/manifests/
```
Or check for them using:
```sh
kubectl get pods --all-namespaces  or kubectl get pods -A
```

### 5️⃣ On which nodes are the static pods created currently?
To see which nodes have static pods running, use:
```sh
kubectl get pods --all-namespaces -o wide
```
Look for pods running with `STATIC` in their description.

---
These questions and commands help understand how Kubernetes schedules DaemonSets and static pods within a cluster.

