# SSH into Minikube Kubernetes Node (Hyper-V, Windows)

This guide walks you through setting up a local Kubernetes cluster using Minikube on Windows with Hyper-V, and how to SSH into the Kubernetes node.

---

## ✅ Prerequisites

Before starting, make sure the following are installed and configured:

- [Hyper-V](https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)

> **Important:** Run all setup commands in **PowerShell as Administrator**.

---

## 🚀 Start Minikube with Hyper-V

```bash
minikube start --driver=hyperv
```

> This will create a virtual machine using Hyper-V and start your local Kubernetes cluster.

<br>

## 🔍 Check Minikube Status

```bash
minikube status
```

<br>

## 🌐 Get Minikube Node IP

```bash
minikube ip
```

> This will return the IPv4 address of the Kubernetes node.

<br>

## 🔐 SSH into the Minikube Node

```bash
minikube ssh
```
> You are now inside the virtual machine (node) running your Kubernetes cluster.

<br>

## 🐳 List Running Containers on the Node

```bash
docker ps
```
> This lists all Docker containers running on the node.

<br>

## 📦 Try kubectl Inside the Node (Will Not Work)

```bash
kubectl get pods
```
- kubectl is not available inside the node.
- kubectl must be used outside the node for managing Kubernetes resources.
- You should exit and run it from your host machine.

<br>

## ⏏️ Exit the Node

```bash
exit
```

<br>

## ✅ Run kubectl on Host Machine

```bash
kubectl get nodes
```
> Now kubectl should work as expected on your local machine.




















