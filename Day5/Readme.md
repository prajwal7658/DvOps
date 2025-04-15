# Kubernetes Deployment via Jenkins

This guide explains how to automate Kubernetes deployments using Jenkins on an Ubuntu-based system or EC2 instance.

## Prerequisites

- Jenkins installed and running
- Kubernetes cluster running (EKS, Minikube, or kubeadm)
- Jenkins user has access to the cluster (`~/.kube/config`)
- Docker installed (optional, for image building)
- Git repository containing Kubernetes YAML files

## Step 1: Install Required Jenkins Plugins

In Jenkins Dashboard:

1. Go to **Manage Jenkins > Manage Plugins**
2. Install the following plugins:
   - Kubernetes CLI Plugin
   - Pipeline Plugin
   - Git Plugin
   - Docker Pipeline Plugin (optional)

## Step 2: Configure Jenkins Credentials

1. Go to **Manage Jenkins > Credentials > Global**
2. Add the following:
   - **Kubeconfig Secret File**: Upload your local `~/.kube/config` file
   - **Git credentials** (for accessing private repositories)
   - **DockerHub credentials** (if pushing Docker images)

## Step 3: Create a Jenkins Pipeline Project

1. Go to **Jenkins Dashboard > New Item**
2. Select **Pipeline**, give it a name, and click OK
3. In the configuration:
   - Choose **Pipeline script from SCM** to connect your Git repository
   - Or use the classic editor to define pipeline steps manually (optional)

## Step 4: Run the Pipeline

1. Click **Build Now**
2. View the logs via **Console Output**
3. Check your Kubernetes cluster using:

   ```bash
   kubectl get pods
   kubectl get svc

