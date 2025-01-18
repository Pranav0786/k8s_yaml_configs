# Kubernetes YAML Configurations

This document contains YAML snippets for Pods, Deployments, and Services. You can copy these snippets to create your own files and run them using `kubectl`.

## How to Use These Snippets

1. Copy the YAML configuration for the resource you want to create.
2. Save it to a file with a `.yaml` extension, such as `resource-name.yaml`.
3. Use the provided `kubectl` command to apply the configuration to your Kubernetes cluster.

## Complete YAML Snippets

```yaml
# Pod Configuration
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
  labels:
    app: my-app
spec:
  containers:
  - name: my-container
    image: nginx
    ports:
    - containerPort: 80


# Run this using 
```bash
kubectl apply -f pod.yaml


---

