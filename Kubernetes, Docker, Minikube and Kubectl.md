# Kubernetes, Docker, Minikube, and Kubectl: A Breakdown

### Kubernetes
* **Definition:** Kubernetes is an open-source platform for managing containerized applications. It automates the deployment, scaling, and management of containerized applications. 
* **Key Features:**
  * **Container orchestration:** Manages the lifecycle of containers, including creation, deployment, scaling, and removal.
  * **Self-healing:** Automatically replaces failed containers and restarts applications.
  * **Declarative configuration:** Uses declarative specifications to define the desired state of the application, allowing Kubernetes to manage the actual state.
  * **Service discovery:** Automatically discovers and registers services within a cluster.
  * **Load balancing:** Distributes traffic across multiple instances of an application.

### Docker
* **Definition:** Docker is a platform for building, shipping, and running applications in containers. 
* **Key Features:**
  * **Containerization:** Packages applications and their dependencies into self-contained units called containers.
  * **Portability:** Containers can run consistently across different environments, from development to production.
  * **Efficiency:** Containers are lightweight and share the host operating system's kernel, improving resource utilization.
  * **Isolation:** Containers are isolated from each other, providing security and preventing conflicts.

### Minikube
* **Definition:** Minikube is a tool for running a single-node Kubernetes cluster locally on your laptop or desktop. 
* **Key Features:**
  * **Local development:** Provides a convenient way to experiment with Kubernetes without setting up a full-fledged cluster.
  * **Easy installation:** Can be installed with a single command.
  * **Integration with other tools:** Works well with tools like Kubectl and Docker Desktop.

### Kubectl
* **Definition:** Kubectl is the command-line tool for interacting with Kubernetes clusters. 
* **Key Features:**
  * **Cluster management:** Allows you to create, delete, and manage Kubernetes clusters.
  * **Resource management:** Enables you to create, delete, and manage Kubernetes resources like pods, deployments, services, and more.
  * **Cluster configuration:** Can be used to configure cluster settings and access credentials.
  * **Troubleshooting:** Helps diagnose and resolve issues within Kubernetes clusters.

**In summary:**

* **Kubernetes** is the orchestrator for containerized applications.
* **Docker** is the platform for creating and running containers.
* **Minikube** is a tool for running a single-node Kubernetes cluster locally.
* **Kubectl** is the command-line interface for interacting with Kubernetes clusters.

# Steps to use Kubernetes, Docker, Minikube, and Kubectl

## Step-1:

**Launch your AWS instance with following preferences:**

- Ubuntu OS
- t2.xlarge (16GB ram)
- 50 GB storage
- HTTP/HTTPS and All traffic (anywhere) enabled

## Step-2:

**Open your instance in PuTTY and use the following commands.**

## Installing Docker, Minikube and Kubectl

### 1. Install Docker:

```bash
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```

- Use the following commands:

```bash
sudo usermod -aG docker $USER
```

- ↑ The command `sudo usermod -aG docker $USER` is used to add the current user to the docker group.


```bash
newgrp docker
```
- ↑ The `newgrp docker` command is used to switch the current group of the active shell to the docker group without having to log out and log back in.


### 2. Installing Kubectl:

```bash
sudo snap install kubectl --classic
```

- Check Kubectl version:

```bash
kubectl version --client
```

### 3. Installing Minikube:

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```

```bash
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

- Check Minikube version:

```bash
minikube version
```

## Now that we have Minikube installed, let’s start a Minikube cluster using the Docker driver:

```bash
minikube start --driver=docker
```

- Check Minikube status:
```bash
minikube status
```

```bash
kubectl cluster-info
```

```bash
kubectl config view
```

```bash
kubectl get nodes
```

```bash
kubectl get pods
```

```bash
minikube dashboard
```
<br>

## Let’s deploy a simple Nginx web server using kubectl:

```bash
kubectl create deployment nginx-web --image=nginx
```

```bash
kubectl expose deployment nginx-web --type NodePort --port=80
```

```bash
kubectl get deployment,pod,svc
```

## Managing Minikube Addons

```bash
minikube addons list
```

```bash
minikube addons enable dashboard
```

```bash
minikube addons enable ingress
```

- The following command will give you a link for your dashboard:

```bash
minikube dashboard --url
```

```bash
kubectl proxy --address='0.0.0.0' --disable-filter=true &
```

```bash
http://server_ip:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/
```
- ↑ In your browser replace `server_ip` with public ip
