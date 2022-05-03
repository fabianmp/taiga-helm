# taiga

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 6.4.2](https://img.shields.io/badge/AppVersion-6.4.2-informational?style=flat-square)

A Helm chart for Taiga

**Homepage:** <https://www.taiga.io/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Fabian Zach | <fabian.zach@methodpark.de> | <https://github.com/fabianmp> |

## Source Code

* <https://github.com/fabianmp/taiga-helm>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | 8.6.2 |
| https://charts.bitnami.com/bitnami | rabbitmq | 8.15.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for Taiga pod |
| async.image.pullPolicy | string | `"IfNotPresent"` | Taiga async pull policy |
| async.image.repository | string | `"taigaio/taiga-back"` | Taiga async image |
| async.image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| async.resources | object | `{}` | Resources for async container |
| backend.extraEnv | object | `{}` | Extra environment variables for Taiga backend |
| backend.image.pullPolicy | string | `"IfNotPresent"` | Taiga backend pull policy |
| backend.image.repository | string | `"taigaio/taiga-back"` | Taiga backend image |
| backend.image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| backend.resources | object | `{}` | Resources for backend container |
| events.image.pullPolicy | string | `"IfNotPresent"` | Taiga events pull policy |
| events.image.repository | string | `"taigaio/taiga-events"` | Taiga events image |
| events.image.tag | string | `"6.4.0"` | Overrides the image tag whose default is the chart appVersion. |
| events.resources | object | `{}` | Resources for events container |
| extraEnv | object | `{}` | Extra environment variables for Taiga containers |
| frontend.extraEnv | object | `{}` | Extra environment variables for Taiga frontend |
| frontend.image.pullPolicy | string | `"IfNotPresent"` | Taiga frontend pull policy |
| frontend.image.repository | string | `"taigaio/taiga-front"` | Taiga frontend image |
| frontend.image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| frontend.resources | object | `{}` | Resources for frontend container |
| fullnameOverride | string | `""` | Override full name of this release |
| imagePullSecrets | list | `[]` | Image pull secrets for Taiga pod |
| ingress.annotations | object | `{}` | Annotations to be added to ingress |
| ingress.enabled | bool | `false` | Enable ingress for Taiga |
| ingress.host | string | `"chart-example.local"` | External hostname for Taiga |
| ingress.tls.enabled | bool | `false` | Enable TLS on ingress |
| ingress.tls.secretName | string | `"chart-example-tls"` | Secret name used for TLS certificate |
| nameOverride | string | `""` | Override name of this release |
| nodeSelector | object | `{}` | Node selector for Taiga pod |
| persistence.enabled | bool | `true` | Enable persistent storage |
| persistence.media.size | string | `"1Gi"` | Size of PVC for media |
| persistence.media.storageClass | string | `""` | Name of storage class for media PVC |
| persistence.static.size | string | `"1Gi"` | Size of PVC for static data |
| persistence.static.storageClass | string | `""` | Name of storage class for static data PVC |
| podAnnotations | object | `{}` | Annotations to be added to the Taiga pod |
| postgresql.postgresqlDatabase | string | `"taiga"` | PostgreSQL database name used by Taiga |
| postgresql.postgresqlPassword | string | `"taiga"` | PostgreSQL password used by Taiga |
| postgresql.postgresqlUsername | string | `"taiga"` | PostgreSQL user used by Taiga |
| rabbitmq.auth.erlangCookie | string | `"secret-taiga-erlang-cookie"` | Erlang cookie |
| rabbitmq.auth.password | string | `"taiga"` | RabbitMQ password used by Taiga |
| rabbitmq.auth.username | string | `"taiga"` | RabbitMQ user used by Taiga |
| rabbitmq.extraConfiguration | string | `"default_vhost = taiga"` | Extra configuration for RabbitMQ |
| rabbitmq.vhost | string | `"taiga"` | RabbitMQ virtual host used by Taiga |
| replicaCount | int | `1` | Number of replicas |
| secretKey | string | `"taiga-secret-key"` | Secret key used for cryptographic signing in Taiga |
| service.ports.backend | int | `8000` | Service port for Taiga backend |
| service.ports.events | int | `8888` | Service port for Taiga events |
| service.ports.frontend | int | `80` | Service port for Taiga frontend |
| service.type | string | `"ClusterIP"` | Service type for Taiga service |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` | Tolerations for Taiga pod |

## Adding a super user

To add an initial super user execute the following command in the ``backend``
container of the Taiga pod:

```sh
python manage.py createsuperuser
```
