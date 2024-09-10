# Guia de configuração do serviço SSH

## Referencias

> [Guia completo para configurar o SSH no Linux de forma segura](https://sempreupdate.com.br/linux/tutoriais/guia-configurar-ssh-seguro-linux/)

## Instalação no Linux

Para instalação executar os seguintes comandos conforme a distribuição:

- Ubuntu/Debian

```sh
sudo apt update
sudo apt install openssh-server
```

- CentOS/Fedora

```sh
sudo dnf install openssh-server
```

Iniciar e ativar o serviço:

```sh
sudo systemctl start ssh
sudo systemctl enable ssh
```

## Ajustes de segurança

TODO