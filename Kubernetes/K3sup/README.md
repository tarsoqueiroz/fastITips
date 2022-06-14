# K3sup

## [K3sup](https://github.com/alexellis/k3sup) (said 'ketchup')

k3sup is a light-weight utility to get from zero to KUBECONFIG with k3s on any local or remote VM. All you need is ssh access and the k3sup binary to get kubectl access immediately.

The tool is written in Go and is cross-compiled for Linux, Windows, MacOS and even on Raspberry Pi.

How do you say it? Ketchup, as in tomato.

## Install k3sup

Install steps on "Download k3sup" at `https://github.com/alexellis/k3sup#download-k3sup-tldr`:

```sh
curl -sLS https://get.k3sup.dev | sh
sudo install -o root -g root -m 0755 k3sup /usr/local/bin/
rm k3sup
k3sup --help
```

## Basic usage

```sh
$ k3sup help              # Help about any command
$ k3sup install           # Install k3s on a server via SSH
$ k3sup join              # Install the k3s agent on a remote host and join it to an existing server
$ k3sup update            # Print update instructions
$ k3sup version           # Print the version

$ k3sup [command] --help  # for more information about a command.
```

## Congrats!

That's all folks!!!
___
