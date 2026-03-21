# MNIST Inference on Kubernetes 

This project demonstrates how to deploy a pre-trained MNIST model on Kubernetes and perform inference in a local development environment using Minikube.

## Components

* Frontend Service
* Inference API
* Model Service
* Kubernetes (Minikube)

## Prerequisites

* Docker
* kubectl
* Minikube

## Deploy

### Start Minikube cluster

```bash
minikube start --driver=docker
```

### Build Docker image

```bash
bash image/k8s.sh
```

### Deploy to Kubernetes

```bash
kubectl apply -f k8s/
```

### Access services

```bash
kubectl port-forward service/frontend-service 8080:80
kubectl port-forward service/api-service 8000:8000
```

## Open Web Interface

Open your browser and navigate to:

http://localhost:8080

Upload data from the dataset/folder.csv

The system will return the predicted digit

## Motivation

While MNIST is a simple dataset, this project focuses on deploying machine learning models in a Kubernetes-based environment rather than training.

Minikube is used to simulate a local Kubernetes cluster for development and testing purposes.

## Notes

This project uses Minikube, which runs a local single-node Kubernetes cluster for development and experimentation.
In a production environment, a multi-node Kubernetes cluster would be required for scalability and high availability.

## Other

Dataset: [Kaggle Digit Recognizer](https://www.kaggle.com/competitions/digit-recognizer/data)