# OpenShift Local

## About

Red Hat OpenShift Local (formerly Red Hat CodeReady Containers) is the quickest way to get started building OpenShift clusters. It is designed to run on a local computer to simplify setup and testing, and to emulate the cloud development environment locally with all of the tools needed to develop container-based applications.

More info:

> `https://developers.redhat.com/products/openshift-local/overview`

## Prereq for OpenShift Container Platform

- 4 physical CPU cores
- 9 GB of free memory
- 35 GB of storage space

Requirements on Linux:

- On Linux, CRC is supported only on the latest two Red Hat Enterprise Linux/CentOS 8 and 9 minor releases and on the latest two stable Fedora releases.
- When using Red Hat Enterprise Linux, the machine running CRC must be registered with the Red Hat Customer Portal.
- Ubuntu 18.04 LTS or later and Debian 10 or later are not supported and might require manual set up of the host machine.

Required software packages for Linux:

Red Hat OpenShift Local requires the libvirt and NetworkManager packages to run on Linux. Consult the following table to find the command used to install these packages for your Linux distribution:

| Linux Distribution | Installation command |
| --- | --- |
| Fedora / Red Hat Enterprise Linux / CentOS | `sudo dnf install NetworkManager` |
| Debian/Ubuntu | `sudo apt install qemu-kvm libvirt-daemon libvirt-daemon-system network-manager` |

## Installing RedHat OpenShift Local

Procedure:

- Download the **latest release** of Red Hat OpenShift Local for your platform and **"Pull secret"** from:

> `https://console.redhat.com/openshift/create/local`

- Assuming the archive is in the ```~/Downloads``` directory, extract the contents of the archive following these steps:

```sh
cd ~/Downloads
tar xvf crc-linux-amd64.tar.xz
```

- Copy the `crc` executable to a general directory:

```sh
sudo cp ~/Downloads/crc-linux-*-amd64/crc /usr/local/bin
```

- Finally, try it:

```sh
crc version
```

## Setting up Red Hat OpenShift Local

Red Hat OpenShift Local presets represent a managed container runtime, and the lower bounds of system resources required by the instance to run it.

### Initial setup

```sh
crc setup
```

### Changing the presets for CPU and Memory (optional)

```sh
# to change CPU's (default 2)
crc config set cpus 4
# to change Memory (default 2048 - 2GB)
crc config set memory 9216
```

## Starting tool

The `crc start` command starts the Red Hat OpenShift Local instance and configured container runtime.

```sh
crc start
```

At end of success start process it's important save finals informations for future use:

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

Copy `oc` tool for this release of the Red Hat OpenShift Local:

```sh
sudo cp ~/.crc/cache/crc_libvirt_4.14.3_amd64/oc /usr/local/bin

# try it
oc version
```

## Playing in "the playground"

Access the OpenShift Container Platform cluster running in the Red Hat OpenShift Local instance:

```sh
# login as kubeadmin with password saved
oc login -u kubeadmin https://api.crc.testing:6443

# 
oc get nodes -o wide

# 
oc describe project default

# 
oc get is -n openshift
```

And try to access the OpenShift Container Platform web console by using your web browser:

- `https://console-openshift-console.apps-crc.testing`

## Congrats

That's all folks!!!
