# MLFlow Server

An MLFlow Server designed to work with OpenShift.

[![Build Image](https://github.com/strangiato/mlflow-server/actions/workflows/build-image.yml/badge.svg)](https://github.com/strangiato/mlflow-server/actions/workflows/build-image.yml)

[![GitHub](https://img.shields.io/badge/GitHub-repo-blue.svg)](https://github.com/strangiato/mlflow-server) [![Quay.io](https://img.shields.io/badge/Quay.io-image-blue.svg)](https://quay.io/repository/troyer/mlflow-server)

## Helm Chart

A Helm chart for deploying mlflow on OpenShift

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.25](https://img.shields.io/badge/AppVersion-1.25-informational?style=flat-square)

### Installing the Chart

To access charts from this from the cli repository add it:

```sh
helm repo add strangiato https://strangiato.github.io/helm-charts/
helm repo update strangiato
helm install mlflow-server mlflow-server
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
  - name: "mflow-server"
    version: "0.1.0"
    repository: "https://strangiato.github.io/helm-charts/"
```

### Source Code

* <https://github.com/strangiato/helm-charts/tree/main/charts/mlflow-server>
* <https://github.com/strangiato/mlflow-server>

### Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://strangiato.github.io/helm-charts/ | postgrescluster | 0.2.2 |

### Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity configuration for the MLFlow Server pod |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| crunchyPostgres.enabled | bool | `true` | Enable creation of a postgres instance using crunchyPostgres operator |
| fullnameOverride | string | `""` | String to fully override fullname template |
| image.pullPolicy | string | `"IfNotPresent"` | The docker image pull policy |
| image.repository | string | `"quay.io/troyer/mlflow-server"` | The image repository to use |
| image.tag | string | Chart appVersion | The image tag to use |
| imagePullSecrets | list | `[]` | The image pull secret for the image repository |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths | list | `[]` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` | String to partially override fullname template (will maintain the release name) |
| nodeSelector | object | `{}` | Node selector for the MlFlow Server pod |
| objectBucketClaim.annotations | object | `{}` | Additional custom annotations for the objectBucketClaim |
| objectBucketClaim.bucketclass | string | `"noobaa-default-bucket-class"` | BucketClass name for the creation of the objectBucketClaim |
| objectBucketClaim.enabled | bool | `true` | Enable creation of s3 bucket with objectBucketClaim for artifact storage |
| objectBucketClaim.storageClassName | string | `"openshift-storage.noobaa.io"` | StorageClassName for creation of the objectBucketClaim |
| podAnnotations | object | `{}` | Map of annotations to add to the pods |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` | replicas of MLFlow Server |
| resources | object | `{}` | Resource configuration for the MLFlow Server pod |
| route.annotations | object | `{}` | Additional custom annotations for the route |
| route.enabled | bool | `true` | Enable creation of the OpenShift Route object |
| route.host | string | Set by OpenShift | The hostname for the route |
| route.path | string | `""` | The path for the OpenShift route |
| route.tls.enabled | bool | `true` | Enable secure route settings |
| route.tls.insecureEdgeTerminationPolicy | string | `"Redirect"` | Insecure route termination policy |
| route.tls.termination | string | `"edge"` | Secure route termination policy |
| securityContext | object | `{}` |  |
| service.port | int | `80` | MLFlow server port |
| service.type | string | `"ClusterIP"` | Kubernetes Service type |
| serviceAccount.annotations | object | `{}` | Additional custom annotations for the ServiceAccount |
| serviceAccount.create | bool | `true` | Enable creation of ServiceAccount for MLFlow Server pod |
| serviceAccount.name | string | fullname template | The name of the ServiceAccount to use. |
| tolerations | list | `[]` | Tolerations for the MLFlow Server pod |
