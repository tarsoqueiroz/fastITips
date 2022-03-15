# Minikube

## What is Minikube?

[minikube](https://minikube.sigs.k8s.io/docs/start/) is local Kubernetes, focusing on making it easy to learn and develop for Kubernetes.

All you need is Docker (or similarly compatible) container or a Virtual Machine environment, and Kubernetes is a single command away: `minikube start`

## Install Minikube

Install steps on "Installation" at `https://minikube.sigs.k8s.io/docs/start/`:

```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## Completion for Minikube

```sh
minikube completion bash | sudo tee /etc/bash_completion.d/minikube_completion
```

## Basic interaction with Minikube

```sh
# Creating miniK8s
minikube start
# Show me the minikube node
minikube node list
# Current context
kubectx -c 
# Show me the nodes on minikube
kubectl get nodes -o wide
# Changing context
kubectx minikube
# Show me the nodes on cluster k3d-k3s-default
kubectl get nodes -o wide
# Deleting clusters
minikube delete
```

## Congrats!

That's all folks!!!
___

