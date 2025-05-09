# KubeBuilder

## About

Kubebuilder is a framework for building Kubernetes APIs using custom resource definitions (CRDs).

Kubebuilder increases velocity and reduces the complexity managed by developers for rapidly building and publishing Kubernetes APIs in Go. It builds on top of the canonical techniques used to build the core Kubernetes APIs to provide simple abstractions that reduce boilerplate and toil.

References:

- [Kubebuilder Book](https://book.kubebuilder.io/)
- [Github](https://github.com/kubernetes-sigs/kubebuilder)
- [Quick install](https://book.kubebuilder.io/quick-start#installation)

## Install kubebuilder

```sh
# get latest version for GOOS and GOARCH env
curl -L -o kubebuilder "https://go.kubebuilder.io/dl/latest/$(go env GOOS)/$(go env GOARCH)"

# install on /usr/local/bin
sudo install -o root -g root -m 0755 kubebuilder /usr/local/bin/kubebuilder

# remove downloaded file
rm kubebuilder
```

## Completion for kubebuilder

```sh
kubebuilder completion bash | sudo tee /etc/bash_completion.d/kubebuilder_completion
```

## Basic usage

```sh
kubebuilder version

kubebuilder help
```

## Congrats

That's all folks!!!
___
