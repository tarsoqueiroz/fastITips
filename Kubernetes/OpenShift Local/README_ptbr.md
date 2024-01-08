# OpenShift Local

## Sobre

Red Hat OpenShift Local (o antigo Red Hat CodeReady Containers) é a forma mais rápida de iniciar a montagem de um cluster OpenShift. O OpenShift Local foi projetado para rodar em um computador local para simplificar a configuração e testes, e para emular um ambiente cloud local com todas as ferramentas necessárias para desenvolver aplicações baseadas em container.

Mais informações em:

> `https://developers.redhat.com/products/openshift-local/overview`

## Prerequisitos

- CPU com 4 cores físicos
- 9 GB de memória disponível
- 35 GB de espaço em disco

Requisitos no Linux:

- Suportado nas versões mais recentes do Red Hat Enterprise Linux/CentOS 8 and 9, e nas duas últimas versões estáveis do Fedora.
- Quando no Red Hat Enterprise Linux, o OpenShift Local deve estar registrado no portal de cliente da Red Hat.
- Versões mais antigas do Ubuntu 18.04 LTS ou Debian 10 não são suportadas, podendo ser necessário configurações manuais na máquina.

Pacotes instalados para o Linux:

Red Hat OpenShift Local precisa dos pacotes do libvirt e NetworkManager para rodar no Linux. A tabela que segue mostra os comandos necessários para a instalação desses pacotes conforme a distribuição utilizada:

| Linux Distribution | Installation command |
| --- | --- |
| Fedora / Red Hat Enterprise Linux / CentOS | `sudo dnf install NetworkManager` |
| Debian / Ubuntu | `sudo apt install qemu-kvm libvirt-daemon libvirt-daemon-system network-manager` |

## Instalação

Procedimentos:

- Fazer o download da **última versão** (**latest release**) do Red Hat OpenShift Local para a plataforma desejada e também do ***"Pull secret"*** do portal da Red Hat (necessário ter cadastro de usuário):

> `https://console.redhat.com/openshift/create/local`

- Assumindo que o arquivo tenha sido baixado no diretório ```~/Downloads```, extrair o conteúdo:

```sh
cd ~/Downloads
tar xvf crc-linux-amd64.tar.xz
```

- Instalar o executável `crc` em um diretório de acesso geral:

```sh
sudo install -o root -g root -m 0755 ~/Downloads/crc-linux-2.30.0-amd64/crc /usr/local/bin/crc
```

- Generar e configurar o *autocompletion* para o shell tipo bash:

```sh
crc completion bash | sudo tee /etc/bash_completion.d/crc_completion
```

- Finalmente, testar:

```sh
crc version
```

## Configurações

As configurações iniciais do Red Hat OpenShift representam a quantidade mínima de recursos exigidos para subir a instância com o ambiente gerenciador de containers.

### Configuração inicial

```sh
crc setup
```

### Modificando os valores de CPU e Memory (opcional)

```sh
# modificar quantidade de CPU's (default 2)
crc config set cpus 4
# modificar quantidade de Memoria (default 2048 - 2GB)
crc config set memory 9216
```

## Iniciando a instância

O comando `crc start` inicia o Red Hat OpenShift Local instance com o gerenciador de containers.

```sh
crc start
```

Termiando com sucesso o processo, é importante salvar algumas informações apresentadas para uso futuro:

```sh
INFO Adding crc-admin and crc-developer contexts to kubeconfig... 

Started the OpenShift cluster.

The server is accessible via web console at:
  https://console-openshift-console.apps-crc.testing

Log in as administrator:
  Username: kubeadmin
  Password: 9Pukj-nnknb-Nk9nZ-kKN8g

Log in as user:
  Username: developer
  Password: developer

Use the 'oc' command line interface:
  $ eval $(crc oc-env)
  $ oc login -u developer https://api.crc.testing:6443
```

- Instalar a ferramenta CLI `oc` da versão do Red Hat OpenShift Local anteriormente instalado:

```sh
sudo install -o root -g root -m 0755 ~/.crc/cache/crc_libvirt_4.14.3_amd64/oc /usr/local/bin/oc
```

- Generar e configurar o *autocompletion* para o shell tipo bash:

```sh
oc completion bash | sudo tee /etc/bash_completion.d/crc_completion
```

- Testar:

```sh
oc version
```

## Usando o ambiente

- Acessar o cluster OpenShift Container Platform na instância do Red Hat OpenShift Local:

```sh
# logar como kubeadmin com a senha informada na instalação
oc login -u kubeadmin https://api.crc.testing:6443

# 
oc get nodes -o wide

# 
oc describe project default

# 
oc get is -n openshift
```

E também acessar o console web do OpenShift Container Platform através de um browser:

- `https://console-openshift-console.apps-crc.testing`

## Parabéns

Instalação concluída!!!
