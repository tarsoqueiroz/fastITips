# NodeJS - Howto Install

## Source tips

> `https://www.treinaweb.com.br/blog/instalando-e-gerenciando-varias-versoes-do-node-js-com-nvm`

## Using NVM

Flex mode to install Node.js, NVM manages versions of the Node.js. On `https://github.com/nvm-sh/nvm#installing-and-updating` can get the last version for install?

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

## Or

wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

- List available versions

```shell
nvm list-remote
```

- Install version

```shell
nvm install lts/erbium
nvm install v14
nvm install v16.20
nvm install v18.16.0
```

- List versions installed

```shell
nvm list
nvm ls
```

- Select version to use

```shell
nvm ls
nvm use lts/fermium
nvm use 16
nvm use 18.16
nvm use 12.22.12
```

- Default version

```sh
nvm ls default
nvm current
nvm alias default v14.21.3
nvm current
nvm use default
nvm current
nvm use v18.16.0
nvm alias default node
nvm ls default
```

- Uninstall version

```sh
nvm install v10.24.1
nvm ls
nvm uninstall v10 # error, version in use
nvm use v18
nvm uninstall v10.24.1
nvm ls
```

## Congrats

That's all folks!!!
___
