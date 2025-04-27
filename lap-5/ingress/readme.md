## Deploying a Basic Ingress in Kubernetes

This section explains how to deploy a basic Ingress resource to expose a service running within your Kubernetes cluster to the outside world.

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: minimal-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: my-app
            port:
              number: 80
Explanation of the Ingress manifest:

apiVersion: networking.k8s.io/v1: Specifies the API version for Ingress resources.
kind: Ingress: Identifies this resource as an Ingress object.
metadata: name: minimal-ingress: Assigns the name "minimal-ingress" to this Ingress configuration.
metadata: annotations: Provides extra metadata to the Ingress controller.
nginx.ingress.kubernetes.io/rewrite-target: /: This is a specific annotation for the Nginx Ingress controller. It instructs the controller to rewrite the path of the incoming request to / before forwarding it to the backend service. This is useful if your service expects all traffic to be rooted at /.
spec: rules: Defines the rules for routing external traffic. Ingress can have multiple rules for different hostnames.
- http: Defines HTTP-specific routing rules.
paths: A list of paths and their corresponding backend configurations.
- path: /: Specifies the path that this rule applies to. In this case, it matches all paths because / with pathType: Prefix matches any request starting with /.
pathType: Prefix: Defines how the path is matched. Prefix means that a request path starting with the specified path will be matched. Other options include Exact and ImplementationSpecific.
backend: Defines the backend service to which traffic matching this path should be forwarded.
service: Specifies the target Kubernetes Service.
name: my-app: The name of the Kubernetes Service that will handle the traffic. Ensure a Service named my-app exists in your cluster.
port: number: 80: The port on the my-app Service where traffic should be sent.
