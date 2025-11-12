# Kubernetes with Minikube

This guide helps you set up a local Kubernetes cluster using Minikube with Kubernetes version 1.33.

## Prerequisites

- [Install Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Install kubectl](https://kubernetes.io/docs/tasks/tools/)

## Setup Instructions

### 1. Start Minikube with Kubernetes 1.33

```bash
minikube start --kubernetes-version=v1.33.0
```

### 2. Verify the Cluster

```bash
kubectl cluster-info
kubectl get nodes
```

### 3. Check Kubernetes Version

```bash
kubectl version
```

## Useful Minikube Commands

```bash
# Stop the cluster
minikube stop

# Delete the cluster
minikube delete

# Check cluster status
minikube status

# Access Kubernetes dashboard
minikube dashboard
```

## Useful kubectl Commands

```bash
# Get resources
kubectl get pods
kubectl get services
kubectl get deployments
kubectl get nodes

# Describe resources (detailed info)
kubectl describe pod <pod-name>
kubectl describe node <node-name>

# Create/apply resources
kubectl apply -f <filename>.yaml
kubectl create -f <filename>.yaml

# Delete resources
kubectl delete pod <pod-name>
kubectl delete -f <filename>.yaml

# View logs
kubectl logs <pod-name>
kubectl logs <pod-name> -f  # follow logs

# Execute commands in pods
kubectl exec -it <pod-name> -- /bin/bash
kubectl exec <pod-name> -- <command>

# Get pod details in different formats
kubectl get pods -o wide
kubectl get pods -o yaml
kubectl get pods -o json
```

## Documentation Links

- [Minikube Documentation](https://minikube.sigs.k8s.io/docs/)
- [Minikube Start Command Reference](https://minikube.sigs.k8s.io/docs/commands/start/)
- [Kubernetes Version Compatibility](https://kubernetes.io/releases/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [kubectl Command Reference](https://kubernetes.io/docs/reference/kubectl/)

## Working with Pods

This repository contains example pod configurations in the `pods/` directory. Apply them using:

```bash
kubectl apply -f pods/<pod-file>.yaml
```

## In-Class Deployment Demo

demo walkthrough covering configmaps, deployments, and services:

```bash
# apply the configmap
kubectl apply -f configmaps/demo-configmap.yaml

# apply the deployment
kubectl apply -f deployments/demo-deployment.yaml

# apply the service
kubectl apply -f services/demo-nodePort.yaml

# get the service url and access the app
minikube service demo-app-service --url
```

verify everything is running:
```bash
kubectl get configmaps
kubectl get deployments
kubectl get pods
kubectl get services
```
