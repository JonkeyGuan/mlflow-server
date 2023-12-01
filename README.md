# MLFlow Server

An MLFlow Server designed to work with OpenShift.

[![Build Image](https://github.com/jonkeyguan/mlflow-server/actions/workflows/build-image.yml/badge.svg)](https://github.com/jonkeyguan/mlflow-server/actions/workflows/build-image.yml)

[![GitHub](https://img.shields.io/badge/GitHub-repo-blue.svg)](https://github.com/strangiato/mlflow-server) [![Quay.io](https://img.shields.io/badge/Quay.io-image-blue.svg)](https://quay.io/repository/troyer/mlflow-server)

# Helm Chart

A Helm chart for deploying mlflow on OpenShift

![Version: 0.5.6](https://img.shields.io/badge/Version-0.5.6-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.0](https://img.shields.io/badge/AppVersion-2.0-informational?style=flat-square)

## Pre-Reqs

This chart utilizes components from the Crunch Postgres Operator and OpenShift Data Foundations in the default configuration.  The chart expects both operators to be installed on the cluster prior to deploying.

## Installing the Chart

To access charts from this from the cli repository add it:

```sh
helm repo add jonkeyguan https://jonkeyguan.github.io/helm-charts/
helm repo update
helm install [release-name] jonkeyguan/mlflow-server
```

To include a chart from this repository in an umbrella chart, include it in your dependencies in your `Chart.yaml` file.

```yaml
apiVersion: v2
name: example-chart
description: A Helm chart for Kubernetes
type: application

version: 0.1.0

appVersion: "1.16.0"

dependencies:
  - name: "mlflow-server"
    version: "0.5.6"
    repository: "https://jonkeyguan.github.io/helm-charts/"
```

## Source Code

* <https://github.com/JonkeyGuan/helm-charts/tree/main/charts/mlflow-server>
* <https://github.com/jonkeyguan/mlflow-server>

