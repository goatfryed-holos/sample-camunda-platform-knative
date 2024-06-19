## Getting started
### Prerequisites
The following cli tools are required
- docker
- kubectl
- k3d
- helm
- kn (knative cli)
- func (knative functions cli)

Also, you want a dns proxy configuration to point *.test to local host

### Setup
If not already available, create k3d default registry on port 5000
```shell
k3d registry create --port 5000
```

Create the cluster
```shell
k3d cluster create --config ./k3d.yaml
```

Setup contour ingress for knative. We pick contour, because it's the easiest to reuse.
https://knative.dev/docs/install/operator/knative-with-operators/#install-the-networking-layer
```shell
kubectl apply --filename https://github.com/knative/net-contour/releases/download/knative-v1.14.2/contour.yaml
```

#### setup knative self managed
See [knative setup](./knative/setup.md)

#### setup camunda self managed
See [camunda setup](camunda-platform/setup.md)