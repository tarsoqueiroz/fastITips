# Helm - The package manager for Kubernetes

## What is Helm?

[Helm](https://helm.sh/) is the best way to find, share, and use software built for Kubernetes.

## Install Helm

[Install(https://helm.sh/docs/intro/install/)] current latest release

- Download your [desired version](https://github.com/helm/helm/releases)

```sh
curl -LO https://get.helm.sh/helm-v3.14.0-linux-amd64.tar.gz
```

- Unpack it:

```sh
tar -zxvf ./helm-v3.14.0-linux-amd64.tar.gz
```

- Install the helm binary:

```shell
sudo install -o root -g root -m 0755 linux-amd64/helm /usr/local/bin/helm
rm -rf linux-amd64
```

## Completion for Helm

```sh
helm completion bash | sudo tee /etc/bash_completion.d/helm_completion
```

## Initialize a Helm Chart Repository

Once you have Helm ready, you can add a chart repository. Check [Artifact Hub](https://artifacthub.io/packages/search?kind=0) for available Helm chart repositories.

```sh
# Adding repo
helm repo add hashicorp https://helm.releases.hashicorp.com
# Updating list
helm repo update
# Listing repos
helm repo list
# Listing charts on repo
helm search repo hashicorp
# Installing a chart
helm install vault hashicorp/vault
```

## Congrats!

That's all folks!!!
___

