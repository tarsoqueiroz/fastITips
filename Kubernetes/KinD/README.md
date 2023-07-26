# KinD - (K)ubernetes (IN) (D)ocker

[kind](https://sigs.k8s.io/kind) is a tool for running local Kubernetes clusters using Docker container “nodes”. kind was primarily designed for testing Kubernetes itself, but may be used for local development or CI.

## Install KinD

```sh
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64

sudo install -o root -g root -m 0755 kind /usr/local/bin/kind

rm kind
```

## Completion for KinD

```sh
kind completion bash | sudo tee /etc/bash_completion.d/kind_completion
```

## Basic interaction with KinD clusters

```sh
# Creating clusters
kind create cluster
kind create cluster --name kind-2
# Show me the clusters
kind get clusters
# Current context
kubectx -c 
# Show me the nodes on cluster
kubectl get nodes -o wide
# Changing context
kubectx kind-kind
# Show me the nodes on cluster
kubectl get nodes -o wide
# Deleting clusters
kind delete cluster 
kind delete cluster --name kind2
```

## Cluster with multiples nodes

- Configuration file `kind-multinode.yaml`:

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
name: multinode
nodes:
- role: control-plane
- role: control-plane
- role: control-plane
- role: worker
- role: worker
- role: worker
```

- So it's time to create and play 

```sh
kind create cluster --config=kind-multinode.yaml
kind get clusters
kubectl get nodes -o wide
```

## Congrats!

That's all folks!!!
___

