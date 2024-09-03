# taiga

![Version: 0.7.0](https://img.shields.io/badge/Version-0.7.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 6.8.1-fabianmp.0.1.0](https://img.shields.io/badge/AppVersion-6.8.1--fabianmp.0.1.0-informational?style=flat-square)

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
| https://charts.bitnami.com/bitnami | postgresql | 14.0.2 |
| https://charts.bitnami.com/bitnami | rabbitmq | 12.10.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for Taiga pod |
| async.image.pullPolicy | string | `"IfNotPresent"` | Taiga async pull policy |
| async.image.repository | string | `"fabianmp/taiga-back"` | Taiga async image |
| async.image.tag | string | `"6.8.1-fabianmp.0.1.0-oidc"` | Overrides the image tag whose default is the chart appVersion. |
| async.resources | object | `{}` | Resources for async container |
| auth.defaultLoginEnabled | bool | `true` | Enable login form for local users |
| auth.oidc.authKey | string | `"oidc"` | Key identifying OAuth users |
| auth.oidc.claims.authData | string | `"sub"` | OAuth user id claim |
| auth.oidc.claims.email | string | `"email"` | OAuth e-mail address claim |
| auth.oidc.claims.fullName | string | `"name"` | OAuth full name claim |
| auth.oidc.claims.userName | string | `"preferred_username"` | OAuth preferred username claim |
| auth.oidc.clientId | string | `nil` | OAuth client id |
| auth.oidc.clientSecret | string | `nil` | OAuth client secret |
| auth.oidc.enabled | bool | `false` | Enable OIDC authentication |
| auth.oidc.endpoints.authorization | string | `nil` | OAuth authorization endpoint |
| auth.oidc.endpoints.jwks | string | `nil` | OAuth JWKS endpoint |
| auth.oidc.endpoints.token | string | `nil` | OAuth token endpoint |
| auth.oidc.endpoints.userinfo | string | `nil` | OAuth user info endpoint |
| auth.oidc.issuer | string | `nil` | Issuer base url |
| auth.oidc.logo | string | `"logo.gif"` | OIDC provider logo |
| auth.oidc.name | string | `"OIDC"` | OIDC provider name |
| auth.oidc.scopes | string | `"openid profile email"` | OAuth scopes |
| auth.oidc.sluggifyUserName | bool | `false` | Sluggify username from claim |
| auth.publicRegisterEnabled | bool | `true` | Enable user signup |
| auth.useForwardedHost | bool | `true` | Use host from X-Forwarded-Host header |
| backend.extraEnv | object | `{}` | Extra environment variables for Taiga backend |
| backend.image.pullPolicy | string | `"IfNotPresent"` | Taiga backend pull policy |
| backend.image.repository | string | `"fabianmp/taiga-back"` | Taiga backend image |
| backend.image.tag | string | `"6.8.1-fabianmp.0.1.0-oidc"` | Overrides the image tag whose default is the chart appVersion. |
| backend.resources | object | `{}` | Resources for backend container |
| events.image.pullPolicy | string | `"IfNotPresent"` | Taiga events pull policy |
| events.image.repository | string | `"taigaio/taiga-events"` | Taiga events image |
| events.image.tag | string | `"6.7.0"` | Overrides the image tag whose default is the chart appVersion. |
| events.resources | object | `{}` | Resources for events container |
| extraEnv | object | `{}` | Extra environment variables for Taiga containers |
| frontend.extraEnv | object | `{}` | Extra environment variables for Taiga frontend |
| frontend.image.pullPolicy | string | `"IfNotPresent"` | Taiga frontend pull policy |
| frontend.image.repository | string | `"fabianmp/taiga-front"` | Taiga frontend image |
| frontend.image.tag | string | `"6.8.1-fabianmp.0.1.0-oidc"` | Overrides the image tag whose default is the chart appVersion. |
| frontend.resources | object | `{}` | Resources for frontend container |
| fullnameOverride | string | `""` | Override full name of this release |
| global.image.tag | string | `""` | Overrides the image tag for all containers whose default is the chart appVersion. |
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
| podAnnotations | object | `{}` | Annotations to be added to the Taiga pod |
| postgresql.auth.database | string | `"taiga"` | PostgreSQL database name used by Taiga |
| postgresql.auth.enablePostgresUser | bool | `false` | PostgreSQL enable postgres admin user |
| postgresql.auth.password | string | `"taiga"` | PostgreSQL password used by Taiga |
| postgresql.auth.username | string | `"taiga"` | PostgreSQL user used by Taiga |
| postgresql.image.tag | string | `"14.10.0-debian-11-r31"` | PostgreSQL version tag |
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
| smtp.enabled | bool | `false` | Enable SMTP backend to send emails |
| smtp.from | string | `""` | Email address Taiga uses to send emails |
| smtp.host | string | `""` | SMTP host to connect to |
| smtp.password | string | `""` | Password for authentication with SMTP server |
| smtp.port | int | `587` | Port for SMTP connection |
| smtp.useSsl | bool | `false` | Use SSL for SMTP connection |
| smtp.useTls | bool | `true` | Use TLS for SMTP connection |
| smtp.username | string | `""` | Username for authentication with SMTP server |
| tolerations | list | `[]` | Tolerations for Taiga pod |

## Adding a super user

To add an initial super user execute the following command in the ``backend``
container of the Taiga pod:

```sh
python manage.py createsuperuser
```
