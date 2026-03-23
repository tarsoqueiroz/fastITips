# Docker Install

> [How To Install and Use Docker on Ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04)

## Installing

```sh
## Update your existing list of packages
sudo apt update

## Install a few prerequisite packages
sudo apt install apt-transport-https ca-certificates curl software-properties-common

## Add the GPG key for the official Docker repository
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

## Add the Docker repository to APT sources
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

## Update your existing list of packages
sudo apt update

## Make sure you are about to install from the Docker repo instead of the default Ubuntu repo
apt-cache policy docker-ce

## Finally, install Docker
sudo apt install docker-ce

## Check that it’s running
sudo systemctl status docker
```

## Executing the Docker Command Without Sudo (Optional)

```sh
## Add your username to the docker group
sudo usermod -aG docker ${USER}

## Apply the new group membership
su - ${USER}

## Confirm
groups
```

## Using Docker

```sh
## View all available subcommands
docker

## To view system-wide information about Docker
docker info
```

## Behind Proxy: Configure the Docker Daemon for image pulls

```sh
## Create a directory for Docker's systemd unit overrides
sudo mkdir -p /etc/systemd/system/docker.service.d

## Create a configuration file /etc/systemd/system/docker.service.d/http-proxy.conf with your proxy details:
[Service]
Environment="HTTP_PROXY=http://proxy.example.com"
Environment="HTTPS_PROXY=https://proxy.example.com"
Environment="NO_PROXY=localhost,127.0.0.1,docker-registry.example.com,.corp"

## Reload the systemd daemon and restart Docker:
sudo systemctl daemon-reload
sudo systemctl restart docker
```

## Working with Docker images

```sh
## To check whether you can access and download images from Docker Hub
docker run hello-world
docker images
docker ps -as
docker rm <CONTAINER ID>
docker run --rm hello-world
docker ps -as

## Searching for images available on Docker Hub
docker search ubuntu

## Download the official ubuntu image
docker pull ubuntu

## To see the images
docker images
```

## Running a Docker Container

```sh
## The combination of the -i and -t switches gives you interactive shell access into the container, and the switch -rm remove container at end of the job
docker run --rm -it ubuntu

## Run these commands inside the container
apt update
apt install nodejs
node -v

exit
```

## Logging to Docker Hub

```sh
## To push your image, first log into Docker Hub
docker login -u <Your Docker registry username>
```

> `WARNING! Your password will be stored unencrypted in /home/tarsoqueiroz/.docker/config.json. Configure a credential helper to remove this warning. See https://docs.docker.com/engine/reference/commandline/login/#credentials-store`

