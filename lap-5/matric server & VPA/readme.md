## Monitoring with Metrics Server and Implementing Vertical Pod Autoscaling (VPA)

This section explains how to install the Metrics Server and deploy a Vertical Pod Autoscaler (VPA) to automatically manage the resource requests and limits of your pods.

### 📊 Installing Metrics Server

The Metrics Server collects resource usage data from nodes and pods in your Kubernetes cluster. HPA and VPA often rely on this data. The provided commands use Helm to install the Metrics Server.

```sh
helm repo add metrics-server [https://kubernetes-sigs.github.io/metrics-server/](https://kubernetes-sigs.github.io/metrics-server/)

helm upgrade --install metrics-server metrics-server/metrics-server \
  --namespace kube-system \
  --set args[0]=--kubelet-insecure-tls,args[1]=--kubelet-preferred-address-types=InternalIP
Explanation of the commands:

helm repo add metrics-server https://kubernetes-sigs.github.io/metrics-server/: This command adds the official Helm repository for Metrics Server to your local Helm configuration. This allows you to easily install packages from that repository.

helm upgrade --install metrics-server metrics-server/metrics-server --namespace kube-system --set args[0]=--kubelet-insecure-tls,args[1]=--kubelet-preferred-address-types=InternalIP: 1  This command installs or upgrades the Metrics Server chart from the added repository.   
1.
github.com
github.com

--install: If a release named metrics-server doesn't exist, Helm will install it. If it does exist, Helm will upgrade it.
metrics-server/metrics-server: Specifies the chart to install, which is named metrics-server within the metrics-server repository.
--namespace kube-system: Deploys the Metrics Server into the kube-system namespace, which is typically used for system-level components.
--set args[0]=--kubelet-insecure-tls,args[1]=--kubelet-preferred-address-types=InternalIP: These --set flags configure command-line arguments for the Metrics Server deployment.
--kubelet-insecure-tls: This flag allows the Metrics Server to communicate with the kubelets over TLS without verifying their certificates. Use with caution in production environments.
--kubelet-preferred-address-types=InternalIP: This flag tells the Metrics Server to prefer using the internal IP addresses of the kubelets when communicating with them.
After running these commands, you can verify if the Metrics Server is running correctly using kubectl top nodes and kubectl top pods -n kube-system.

⚙️ Implementing Vertical Pod Autoscaling (VPA)
Vertical Pod Autoscaler automatically adjusts the CPU and memory requests and limits of your pods over time to optimize resource utilization and potentially improve stability. The provided YAML defines a VPA resource.

YAML

apiVersion: autoscaling.k8s.io/v1
kind: VerticalPodAutoscaler
metadata:
  name: my-app-vpa
spec:
  targetRef:
    apiVersion: "apps/v1"
    kind: Deployment
    name: nginx
  updatePolicy:
    updateMode: "Auto"
Explanation of the VPA manifest:

apiVersion: autoscaling.k8s.io/v1: Specifies the API version for the VerticalPodAutoscaler.
kind: VerticalPodAutoscaler: Identifies this resource as a VPA object.
metadata: name: my-app-vpa: Assigns the name "my-app-vpa" to this VPA configuration.
spec: targetRef: Defines the target resource that this VPA will manage.
apiVersion: "apps/v1": Specifies the API version of the target resource (in this case, apps/v1 for Deployments).
kind: Deployment: Indicates the type of the target resource is a Deployment.
name: nginx: Specifies the name of the Deployment whose pods will be managed by this VPA.
spec: updatePolicy: Defines how the VPA should apply resource updates to the pods.
updateMode: "Auto": This mode allows the VPA to automatically update the pod's resource requests and limits by evicting and recreating the pods. Other modes like "Initial" (only set resources on pod creation) and "Off" (only provide recommendations) exist.







Canvas
