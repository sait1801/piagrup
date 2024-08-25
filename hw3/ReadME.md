# Flask Application Deployment with Kubernetes

This repository contains a Flask application and Kubernetes configuration files for deploying the app using Kubernetes.

## Prerequisites

- Docker installed on your local machine
- Kubernetes cluster (Minikube, Docker Desktop with Kubernetes, or a cloud-based cluster)
- kubectl CLI tool installed
- Helm package manager installed
- (Optional) If you want to use ingress, you need to insstall helm charts:
  ````bash
      helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
      helm repo update
      helm install ingress-nginx ingress-nginx/ingress-nginx --namespace hw3
      ```
  ````

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```

### 2. Create namespace

```bash
kubectl create namespace hw3
```

### 3. Deploy the Application

#### 3.1 Deploy USing normal deployment + Loadbalancer service

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

```

#### 3.2 Deploy as ReplicaSet + Ingress service

```bash
kubectl apply -f deployment-replicaset.yaml
kubectl apply -f service-ingress.yaml
kubectl apply -f ingress.yaml
```

### 4. Update Your Local Host File

Add your custom domain name address line to your /etc/hosts file (on Windows: C:\Windows\System32\drivers\etc\hosts):

```bash
127.0.0.1 flaskapp.localhost
```
