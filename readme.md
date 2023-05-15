# Kubernetes Cluster Deployment with Docker Container

This repository provides a guide and resources for deploying a Kubernetes cluster using Docker containers. It aims to simplify the process of setting up and managing a Kubernetes cluster, enabling you to focus on developing and deploying applications.

## Prerequisites

Before getting started, ensure that you have the following prerequisites installed:

- Docker: [Install Docker](https://docs.docker.com/engine/install/)
- Kubernetes: [Install Kubernetes](https://kubernetes.io/docs/setup/)
- kubectl: [Install kubectl](https://kubernetes.io/docs/tasks/tools/)

## Getting Started

To deploy the Kubernetes cluster using the provided Docker container, follow these steps:

1. Clone this repository to your local machine:

```bash
git clone https://github.com/mohammad767/java-docker.git
cd java-docker
```

2. Build the Docker image using the provided Dockerfile:

```bash
docker build -t java-docker .
```

3. Start the Kubernetes cluster:

```bash
minikube start
```

4. Wait for the cluster to be provisioned. You can check the status using:

```bash
kubectl get nodes
```

5. Deploy your application to the Kubernetes cluster(make sure that you are in the same deployment.yaml directory):

```bash
kubectl apply -f deployment.yaml
```

6. Verify that your application is running:

```bash
kubectl get pods
```

You should see your application's pod in the list, indicating a successful deployment.

## Customizing the Deployment

You can customize the deployment by modifying the Kubernetes configuration files provided in the `/spring-petclinic-main/deployment.yaml`. Adjust the resources, environment variables, and other parameters according to your application's requirements.

- `deployment.yaml`: Contains the deployment specification for your application.

Feel free to explore and adapt these files to fit your specific needs.

Accessing the Application
-------------------------

To access the application, you will need to access the NodePort service for the k8s-demo-app container by navigating to `http://<node-ip>:<node-port>` in your web browser.

Cleaning Up
-----------

To delete the MongoDB and k8s-demo-app deployments, run the following command:
```
kubectl delete deployment deployment.yaml
```

To delete the NodePort service, run the following command:
```
kubectl delete service webapp-service
```

Conclusion
----------
this is just an example on how to deploy a Kubernetes cluster using a docker image
