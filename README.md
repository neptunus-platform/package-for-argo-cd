# Argo CD

This project provides a [Carvel package](https://carvel.dev/kapp-controller/docs/latest/packaging) for [Argo CD](https://argoproj.github.io/cd), a declarative and GitOps continuous delivery tool for Kubernetes.

## Components

* argo-cd

## Configuration

The Argo CD package has the following configurable properties.

| Value | Required/Optional | Description |
|-------|-------------------|-------------|
| `service.type` | Optional | The type of Kubernetes service to provision for the Argo CD Server. Valid values are `LoadBalancer`, `NodePort`, and `ClusterIP`. By default, it's `ClusterIP`. |

```yaml
service:
  type: ClusterIP
```

## Prerequisites

Before installing the Argo CD package, you need to add [the Neptunus Platform package repository](https://github.com/neptunus-platform/package-repository) to your cluster.

## Installation

You can install the Argo CD package using `kctrl`:

   ```shell
   kctrl package install --package-install argo-cd \
     --package argo-cd.neptunus.thomasvitale.com \
     --version ${ARGOCD_PACKAGE_VERSION}
   ```

   > You can get the `${ARGOCD_PACKAGE_VERSION}` from running `kctrl
   > package available list -p argo-cd.neptunus.thomasvitale.com`.
   > Specifying a namespace may be required depending on where your package
   > repository was installed.

## Documentation

For documentation specific to Argo CD, check out [https://argoproj.github.io/cd](https://argoproj.github.io/cd).
