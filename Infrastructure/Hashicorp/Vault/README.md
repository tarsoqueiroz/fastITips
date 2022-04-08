# Vault - The package manager for Kubernetes

## What is Vault?

[Vault](https://www.vaultproject.io/) is an identity-based secrets and encryption management system. A secret is anything that you want to tightly control access to, such as API encryption keys, passwords, or certificates. Vault provides encryption services that are gated by authentication and authorization methods. Using Vault’s UI, CLI, or HTTP API, access to secrets and other sensitive data can be securely stored and managed, tightly controlled (restricted), and auditable.

## Install Vault

- By package manager for [Ubuntu/Debian](https://www.vaultproject.io/downloads):

```sh
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt-get update && sudo apt-get install vault
```

## Autocompletion for Vault

```sh
vault -autocomplete-install
```

## Test

```sh
vault --help
vault --version
```

## Congrats!

That's all folks!!!
___
