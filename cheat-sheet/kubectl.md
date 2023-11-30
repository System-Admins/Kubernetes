# Cheat Sheet for KUBECTL

This page shows a examples and simple commands that can help you on the way with KUBECTL for Kubernetes.

```shell
# Get all resource from all namespaces
kubectl get all --all-namespaces

# Get all resource from specific namespace
kubectl get all --namespace=<namespace name>

# Expose a deployment (remember to add ports in the definition file prior)
kubectl expose deployment <name>

# Get endpoints
kubectl get endpoints

# Remove taint from controlplane (dash at the end indicates a removal)
kubectl taint nodes --all node-role.kubernetes.io/control-plane-

# Drain pods.
kubectl drain <node> --ignore-daemonsets

# Get upgrade plan for Kubernetes node
sudo kubeadm upgrade plan

# Create namespace.
kubectl create namespace <namespace name>

# Generate a token (can be used by HTTP REST methods)
kubectl create token default

# Get all API resources groups
kubectl api-resources

# Check permissions
kubectl auth can-i create deployments

# Explain a resource (can be used to get fields for a resource)
kubectl explain pod

# Futher explain spec under pod
kubectl explain pod.spec

# Scale a deployment to 4 pods
kubectl scale deploy/<name> --replicas=4

# Set image on a deployment
kubectl set image deployment <deployment> <image>=<image>:<version>

# Describe a deployment
kubectl describe deployment <name>

# Annotate a deployment
kubectl annotate deployments <name> <annotation key>=<annotation value>

# Undo a deployment
kubectl rollout undo deployment <deployment>

# View the rollout history
kubectl rollout history deployment <deployment>

# Delete a pod using labels.
kubectl delete pod -l <label key>=<label value>

# Show labels on nodes.
kubectl get nodes --show-labels

# Label node.
kubectl label node <node> <key>=<value>
```
