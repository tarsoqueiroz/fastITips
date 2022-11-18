# K3d - Lightweight wrapper to run (K3)s in (d)ocker

## What is k3d?

[k3d](https://k3d.io/) is a lightweight wrapper to run k3s (Rancher Lab’s minimal Kubernetes distribution) in docker.

k3d makes it very easy to create single- and multi-node k3s clusters in docker, e.g. for local development on Kubernetes.

Note: k3d is a community-driven project, that is supported by Rancher (SUSE) and it’s not an official Rancher (SUSE) product.

[kind](https://sigs.k8s.io/kind) is a tool for running local Kubernetes clusters using Docker container “nodes”. kind was primarily designed for testing Kubernetes itself, but may be used for local development or CI.

## Install K3d

Install or update to current latest release:

- wget: 

```sh
wget -q -O - https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
```

- curl: 

```sh
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
```

## Completion for K3d

```sh
k3d completion bash | sudo tee /etc/bash_completion.d/k3d_completion
```

## Basic interaction with KinD clusters

```sh
# Creating clusters
k3d cluster create
k3d cluster create k3d-cluster
# Show me the clusters
k3d cluster list
# Current context
kubectx -c 
# Show me the nodes on cluster k3d-k3d-cluster
kubectl get nodes -o wide
# Changing context
kubectx k3d-k3s-default
# Show me the nodes on cluster k3d-k3s-default
kubectl get nodes -o wide
# Deleting clusters
k3d cluster delete
k3d cluster delete k3d-cluster
```

## Cluster with multiples nodes

- Configuration file `k3d-multinode.yaml`:

```yaml
# k3d configuration file, saved as e.g. /home/me/myk3dcluster.yaml
apiVersion: k3d.io/v1alpha4      # this will change in the future as we make everything more stable

kind: Simple                     # internally, we also have a Cluster config, which is not yet available externally

metadata:
  name: multinode                # name that you want to give to your cluster (will still be prefixed with `k3d-`)

servers: 3                       # same as `--servers 3`
agents: 3                        # same as `--agents 3`

kubeAPI:                         # same as `--api-port 0.0.0.0:6443` (where the name would resolve to 0.0.0.0)
# host: "my.k3d.domain"          # important for the `server` setting in the kubeconfig
  hostIP: "0.0.0.0"              # where the Kubernetes API will be listening on
  hostPort: "6443"               # where the Kubernetes API listening port will be mapped to on your host system

image: rancher/k3s:v1.23.6-k3s1  # same as `--image rancher/k3s:v1.23.6-k3s1`
```

- So it's time to create and play 

```sh
k3d cluster create --config ./k3d-multinode.yaml
k3d cluster list
k3d node list
kubectl get nodes -o wide
```

## Congrats!

That's all folks!!!
___

