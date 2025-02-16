# Kubernetes YAML Configurations

This document contains YAML snippets for Pods, Deployments, and Services. You can copy these snippets to create your own files and run them using `kubectl`.

## How to Use These Snippets

1. Copy the YAML configuration for the resource you want to create.
2. Save it to a file with a `.yaml` extension, such as `resource-name.yaml`.
3. Use the provided `kubectl` command to apply the configuration to your Kubernetes cluster.

## YAML Snippets

```yaml
# Pod Configuration
apiVersion: v1
kind: Pod
metadata:
  name: wlug-meta
  labels:
    app: wlug-meta
spec:
  containers:
  - name: my-container
    image: nginx
    ports:
    - containerPort: 80
```

------

```yaml
# Deployment Configuration
apiVersion: apps/v1
kind: Deployment
metadata:
  name: meta-deploy
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```


```yaml
#Service Configuration
apiVersion: v1
kind: Service
metadata:
  name: backend-service
spec:
  selector:
    app: backend
  ports:
  - protocol: TCP
    port: 80
    targetPort: 8080
  type: ClusterIP


```

-----


```yaml
#Amazon-Books-Deploy Configuration
apiVersion: apps/v1
kind: Deployment
metadata:
  name: amazon-books
spec:
  replicas: 2
  selector:
    matchLabels:
      app: amazon-books
  template:
    metadata:
      labels:
        app: amazon-books
    spec:
      containers:
      - name: amazon-books-container
        image: nginx:latest
        ports:
        - containerPort: 80
```

------

```yaml
#Amazon-Books-Service Configuration
apiVersion: v1
kind: Service
metadata:
  name: amazon-books-service
spec:
  type: LoadBalancer
  selector:
    app: amazon-books
  ports:
    - protocol: TCP
      port: 80       # External port
      targetPort: 80  # Port inside the Pod
```

------
