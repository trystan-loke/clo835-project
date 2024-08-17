
# Full-Stack Kubernetes Deployment

## Overview
This project demonstrates the deployment of a multi-tier full-stack application on Kubernetes. The architecture includes:
- **MongoDB Database Tier**
- **Node.js Backend Tier**
- **Nginx Web Tier**

Key Kubernetes resources used in this project:
- **Persistent Volumes & Persistent Volume Claims** for MongoDB data storage
- **ConfigMaps & Secrets** to manage configuration and sensitive data
- **Namespaces** for resource isolation
- **Deployments & Services** to manage application components

The project is deployed locally using **Minikube** to simulate a Kubernetes cluster.

## Deployment Steps

1. Create a namespace for the application:
    ```bash
    kubectl create namespace fullstack-app
    ```

2. Apply the configuration for environment variables and secrets:
    ```bash
    kubectl apply -f configmap.yml
    kubectl apply -f secret.yml
    ```

3. Set up persistent storage for MongoDB:
    ```bash
    kubectl apply -f mongo-pv.yml
    kubectl apply -f mongo-pvc.yml
    ```

4. Deploy MongoDB:
    ```bash
    kubectl apply -f mongo-deployment.yml
    kubectl apply -f mongo-service.yml
    ```

5. Deploy the Node.js backend:
    ```bash
    kubectl apply -f backend-deployment.yml
    kubectl apply -f backend-service.yml
    ```

6. Deploy the Nginx web server:
    ```bash
    kubectl apply -f web-deployment.yml
    kubectl apply -f web-service.yml
    ```

## Conclusion
Once all components are deployed, the full-stack application will be running within the Kubernetes cluster managed by Minikube. This setup demonstrates a scalable and modular approach to deploying a full-stack application with Kubernetes.
