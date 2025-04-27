
## Exploring Kubernetes Gateway API

This section introduces the Kubernetes Gateway API, a modern and flexible way to manage external access to services within your cluster. We'll look at the key resources involved in defining how external traffic is routed.

### 🌐 Defining a `GatewayClass`

A `GatewayClass` acts as a template for creating `Gateway` resources. It defines the type of gateway controller that will manage the Gateways of this class.

```yaml
apiVersion: gateway.networking.k8s.io/v1
kind: GatewayClass
metadata:
  name: nginx
spec:
  controllerName: nginx.org/gateway-controller
Explanation:

apiVersion: gateway.networking.k8s.io/v1: Specifies the API version for the Gateway API.
kind: GatewayClass: Identifies this resource as a GatewayClass.
metadata: name: nginx: Assigns the name "nginx" to this GatewayClass.
spec: controllerName: nginx.org/gateway-controller: Indicates that Gateways belonging to this class will be managed by a controller with the name nginx.org/gateway-controller. This is specific to the Nginx Gateway implementation.
🚪 Creating a Gateway
A Gateway is an instance of a GatewayClass and configures the network endpoint that external traffic can access. It defines listeners on specific ports and protocols.

YAML

apiVersion: gateway.networking.k8s.io/v1
kind: Gateway
metadata:
  name: nginx-gateway
  namespace: default
spec:
  gatewayClassName: nginx
  listeners:
  - name: http
    protocol: HTTP
    port: 80
    allowedRoutes:
      namespaces:
        from: All
Explanation:

apiVersion: gateway.networking.k8s.io/v1: Specifies the API version for the Gateway API.
kind: Gateway: Identifies this resource as a Gateway.
metadata: name: nginx-gateway: Assigns the name "nginx-gateway" to this Gateway.
metadata: namespace: default: Specifies that this Gateway resides in the default namespace.
spec: gatewayClassName: nginx: Links this Gateway to the nginx GatewayClass defined earlier.
spec: listeners: Defines a list of network listeners.
name: http: Gives the listener a name "http".
protocol: HTTP: Specifies that this listener handles HTTP traffic.
port: 80: Configures the listener to listen on port 80.
allowedRoutes: namespaces: from: All: Allows routes from all namespaces to be associated with this listener.
🚦 Defining Routing Rules with HTTPRoute
An HTTPRoute specifies how HTTP traffic arriving at a Gateway should be routed to backend services.

YAML

apiVersion: gateway.networking.k8s.io/v1
kind: HTTPRoute
metadata:
  name: basic-route
  namespace: default
spec:
  parentRefs:
  - name: nginx-gateway
  rules:
  - matches:
    - path:
        type: PathPrefix
        value: /
    backendRefs:
    - name: my-app
      port: 80
Explanation:

apiVersion: gateway.networking.k8s.io/v1: Specifies the API version for the Gateway API.
kind: HTTPRoute: Identifies this resource as an HTTPRoute.
metadata: name: basic-route: Assigns the name "basic-route" to this HTTPRoute.
metadata: namespace: default: Specifies that this HTTPRoute resides in the default namespace.
spec: parentRefs: References the Gateway that this route is attached to.
name: nginx-gateway: Links this route to the "nginx-gateway" Gateway.
spec: rules: Defines a list of routing rules.
matches: Specifies conditions for matching incoming HTTP requests.
path: type: PathPrefix: value: /: Matches any request where the path starts with /.
backendRefs: Defines where matching requests should be forwarded.
name: my-app: Specifies the name of the backend Kubernetes Service ("my-app").
port: 80: Specifies the port on the backend Service to forward traffic to.
