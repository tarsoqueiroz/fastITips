# KubeCTL

## kubectl

The Kubernetes command-line tool, [kubectl](https://kubernetes.io/docs/reference/kubectl/kubectl/), allows you to run commands against Kubernetes clusters. You can use kubectl to deploy applications, inspect and manage cluster resources, and view logs. For more information including a complete list of kubectl operations, see the [`kubectl` reference documentation](https://kubernetes.io/docs/reference/kubectl/).

**[Before you begin](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#before-you-begin)**

You must use a kubectl version that is within one minor version difference of your cluster. For example, a v1.23 client can communicate with v1.22, v1.23, and v1.24 control planes. Using the latest compatible version of kubectl helps avoid unforeseen issues.

## Install kubectl

Install steps on "Installation" at `https://minikube.sigs.k8s.io/docs/start/`:

```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
rm kubectl
```

## Completion for kubectl

```sh
kubectl completion bash | sudo tee /etc/bash_completion.d/kubectl_completion
```

## Basic usage

```sh
kubectl version --client -o yaml

kubectl --help
```

## Congrats!

That's all folks!!!
___
