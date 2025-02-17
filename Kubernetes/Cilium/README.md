# Cilium

Cilium is open source software for transparently securing the network connectivity between application services deployed using Linux container management platforms like Docker and Kubernetes.

## Release versions

> [`https://github.com/kubernetes-sigs/kind/releases`](https://github.com/kubernetes-sigs/kind/releases)

## Quick install Cilio CLI

```sh
curl -L --remote-name-all https://github.com/cilium/cilium-cli/releases/latest/download/cilium-linux-amd64.tar.gz{,.sha256sum}

sha256sum --check cilium-linux-amd64.tar.gz.sha256sum

sudo tar xzvfC cilium-linux-amd64.tar.gz /usr/local/bin

rm cilium-linux-amd64.tar.gz{,.sha256sum}
```

## Completion for KinD

```sh
cilium completion bash | sudo tee /etc/bash_completion.d/cilium_completion
```

## Verify CLI install

```sh
cilium version
```

## Install Cilium

```sh
# Creating clusters
kind create cluster --name kindilium --config=kind-cilium-v1.10.yaml
# Show me the clusters
kind get clusters
# Install Cilium
cilium install
# Validate the installation
cilium status --wait
# Validate the network connectivity
cilium connectivity test
```

## Congrats! That's

...all folks!!!
