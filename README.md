---

# Setting Up Minikube  
## Container Orchestration with Kubernetes

Imagine orchestrating a vibrant culinary event with various chefs preparing different dishes. Just like a skilled event planner brings order to the chaos, **container orchestration** ensures each chef (container) delivers the perfect serving on time. One notable orchestrator is **Kubernetes**, which coordinates containers to deliver seamless application performance.

Container orchestration automates the **deployment, scaling, and operation** of containerized applications, ensuring high availability and optimal performance. **Kubernetes**, originally developed by Google, has become the de facto standard for container orchestration.

---

## What is Kubernetes?

**Kubernetes** is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. It provides:

- Centralized control of applications
- Automated load balancing
- Self-healing capabilities
- Seamless rolling updates

---

## Components of a Kubernetes Cluster  
### 1. Control Plane (Master Node)

The **Control Plane** manages the entire cluster and consists of:

- **API Server**: Exposes the Kubernetes API; acts as the front end.
- **Scheduler**: Assigns workloads to nodes based on resource availability.
- **Controller Manager**: Maintains the desired state of the cluster.
- **etcd**: Distributed key-value store holding all cluster data.

### 2. Nodes (Worker Nodes)

Nodes are individual machines where containerized applications run. Each node includes:

- **Container runtime** (e.g., Docker)
- **Kubelet**: Communicates with the control plane and manages pods on the node.
- **Kube-proxy**: Manages network communication inside and outside the cluster.

### 3. Pods

A **Pod** is the smallest deployable unit in Kubernetes. It encapsulates one or more containers that:

- Share storage and networking
- Are always scheduled together on the same node

### 4. Containers

Containers package applications and dependencies into a lightweight, portable unit. Kubernetes manages containers through pods.

---

## Kubernetes Architecture (Components Overview)

| Component        | Role |
|------------------|------|
| **API Server**   | Interface for all cluster interactions |
| **Controller Manager** | Enforces desired cluster state |
| **Scheduler**    | Assigns pods to available nodes |
| **etcd**         | Stores all cluster data |
| **Kubelet**      | Manages containers on a node |
| **Kube-proxy**   | Handles networking between services and pods |

---

## Project Prerequisites

Before starting, ensure:

- Completion of **Foundations Core Program 1 & 2**
- **2 CPUs or more**
- **2GB RAM minimum**
- **20GB disk space**

---

## Project Goals

By the end of this project, you should be able to:

- Understand core Kubernetes concepts
- Use **Minikube** to deploy local clusters
- Gain hands-on experience with **Docker**
- Build and deploy applications on Minikube

---

# What is Minikube?

**Minikube** is an open-source tool that lets you run Kubernetes locally. It simulates a Kubernetes environment on your machine, making it ideal for learning, testing, and development.

---

## Getting Started with Minikube

### 🔧 Windows Installation

1. **Open terminal as Administrator**
2. **Install Minikube using Chocolatey**  
```bash
choco install minikube
```
> If Chocolatey is not installed, [follow this guide](https://docs.chocolatey.org/en-us/choco/setup/).

3. **Install Docker Desktop** for Windows ([official guide](https://docs.docker.com/desktop/install/windows-install/))
4. **Start Minikube with Docker as the driver**  
```bash
minikube start --driver=docker
```

---

### 🐧 Linux Installation

1. **Open terminal with sudo access**
2. **Install Docker and prerequisites**  
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl status docker
```

3. **Install Minikube**  
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
```

4. **Start Minikube**  
```bash
minikube start --driver=docker
```

5. **Install `kubectl`**  
```bash
sudo snap install kubectl --classic
```

---

### 🍎 macOS Installation

1. **Open terminal with admin privileges**
2. **Install Minikube**  
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
sudo install minikube-darwin-amd64 /usr/local/bin/minikube
```

3. **Install Docker Desktop** from [official site](https://docs.docker.com/desktop/install/mac-install/)
4. **Start Minikube**  
```bash
minikube start --driver=docker
```

---
