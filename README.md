# Kubiya Operator Helm Chart

Welcome to the Helm chart repository for Kubiya Operator! This chart deploys the Kubiya Operator on a Kubernetes cluster using the Helm package manager.

## Prerequisites

- Kubernetes 1.19+
- Helm 3.1.0

## Installing the Chart

To install the chart with the release name `my-kubiya-operator`:

```bash
helm repo add kubiya-operator https://your-username.github.io/kubiya-operator-helm/
helm repo update
helm install my-kubiya-operator kubiya-operator/kubiya-operator
```

This command deploys Kubiya Operator on the Kubernetes cluster in the default configuration. The Parameters section lists the parameters that can be configured during installation.

## Uninstalling the Chart
To uninstall/delete the my-kubiya-operator deployment:
```bash
helm delete my-kubiya-operator
```
This command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters

The following table lists the configurable parameters of the Kubiya Operator chart and their default values.

| Parameter            | Description                          | Default                          |
|----------------------|--------------------------------------|----------------------------------|
| `replicaCount`       | Number of Kubiya Operator replicas   | `1`                              |
| `image.repository`   | Kubiya Operator image name           | `ghcr.io/kubiyabot/kubiya-operator` |
| `image.tag`          | Kubiya Operator image tag            | `stable`                         |
| `image.pullPolicy`   | Image pull policy                    | `IfNotPresent`                   |
| `service.type`       | Kubernetes Service type              | `ClusterIP`                      |
| `service.port`       | Service HTTP port                    | `80`                             |
| `ingress.enabled`    | Enable ingress for the service       | `false`                          |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example:

```bash
helm install my-kubiya-operator \
  --set image.tag=latest \
  kubiya-operator/kubiya-operator
```

## Configuration and Installation Details
### Default Configuration
This chart deploys the Kubiya Operator with minimal setup and a default configuration. It is highly recommended to review and modify the values.yaml file according to your deployment requirements.

### Customizing the Installation
To handle more complex configurations and to specify parameters for the installation, use either the --values or --set methods:

* Use the --values (or -f) option to specify a custom values.yaml:
```bash
helm install my-kubiya-operator -f my-values.yaml kubiya-operator/kubiya-operator
```
* Use the --set option to override one or more values:
```bash
helm install my-kubiya-operator kubiya-operator/kubiya-operator --set nameOverride=my-new-name
```