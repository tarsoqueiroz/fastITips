# Helm - The package manager for Kubernetes

## What is arkade?

[arkade](https://github.com/alexellis/arkade) is how developers install the latest versions of their favourite tools and Kubernetes apps.

With `arkade get`, you'll have `kubectl`, `kind`, `terraform`, and `jq` on your machine faster than you can type `apt-get install/brew update`.

## Install arkade

- Download and install arkade

```s
curl -sLS https://get.arkade.dev | sudo sh
```

## Completion for arkade

```sh
arkade completion bash | sudo tee /etc/bash_completion.d/arkade_completion
```

## Try it

Once you have arkade ready, try it.

```sh
# simple run
arkade
# help
arkade --help
# infor about app (openfaas)
arkade info openfaas
```

## Congrats!

That's all folks!!!
___

