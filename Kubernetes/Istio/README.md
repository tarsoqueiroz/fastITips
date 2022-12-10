# Istio - The Istio service mesh

## What's Isto Service Mesh?

[Istio](https://istio.io/) addresses the challenges developers and operators face with a distributed or microservices architecture. Whether you're building from scratch or migrating existing applications to cloud native, Istio can help.

## Install `istioctl`

Go to the Istio release page to download the installation file for your OS, or download and extract the latest release automatically (Linux or macOS):

```s
cd ~/Downloads

curl -L https://istio.io/downloadIstio | sh -
cd istio-<version>

sudo install -o root -g root -m 0755 bin/istioctl /usr/local/bin/
```￼

Completion for Istio control shuld be executed this:

```s
istioctl completion bash | sudo tee /etc/bash_completion.d/istio_completion
```

## Install Istio

For this installation, we use the demo configuration profile. It’s selected to have a good set of defaults for testing, but there are other profiles for production or performance testing.

> *If your platform has a vendor-specific configuration profile, e.g., Openshift, use it in the following command, instead of the demo profile. Refer to your platform instructions for details.*

```s
istioctl install --set profile=demo -y
✔ Istio core installed
✔ Istiod installed
✔ Egress gateways installed
✔ Ingress gateways installed
✔ Installation complete
```

Add a namespace label to instruct Istio to automatically inject Envoy sidecar proxies when you deploy your application later:

```s
kubectl label namespace default istio-injection=enabled
namespace/default labeled
```

## Try more

To deploy the sample application go to `https://istio.io/latest/docs/setup/getting-started/#bookinfo`

## Congrats!

That's all folks!!!
___

