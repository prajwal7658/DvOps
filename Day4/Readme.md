# Kubernetes Setup and Basic Usage Guide (Ubuntu)

This guide helps you install Kubernetes tools (kubectl and Minikube), start a local cluster, and deploy a sample application.

## Step 1: Install kubectl (Kubernetes CLI)

1. Download the latest version

   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

2. Make it executable

   chmod +x kubectl

3. Move it to a system path

   sudo mv kubectl /usr/local/bin/

4. Check the version

   kubectl version --client

## Step 2: Install Minikube (Local Kubernetes Cluster)

1. Download Minikube

   curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

2. Make it executable

   chmod +x minikube-linux-amd64

3. Move it to a system path

   sudo mv minikube-linux-amd64 /usr/local/bin/minikube

4. Start Minikube

   minikube start

5. Check the status

   minikube status

## Step 3: Create a Sample Deployment

1. Create a simple deployment

   kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4

2. Expose the deployment as a service

   kubectl expose deployment hello-node --type=NodePort --port=8080

3. Get the URL to access it

   minikube service hello-node --url

## Step 4: Useful Kubernetes Commands

- Get all pods  
  kubectl get pods

- Get all deployments  
  kubectl get deployments

- Get all services  
  kubectl get services

- Delete a deployment  
  kubectl delete deployment hello-node

- Delete a service  
  kubectl delete service hello-node



