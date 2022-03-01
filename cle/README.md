# cle

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: 0.1.0](https://img.shields.io/badge/AppVersion-0.1.0-informational?style=flat-square)

A Helm chart to install ChaosNative Litmus Enterprise

**Homepage:** <https://chaosnative.com>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Raj Babu Das | raj@chaosnative.com |  |

## Source Code

* <https://github.com/chaosnative/cle>

## Requirements

Kubernetes: `>=1.16.0-0`

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| adminConfig.DBPASSWORD | string | `"1234"` |  |
| adminConfig.DBUSER | string | `"admin"` |  |
| adminConfig.DB_PORT | string | `"27017"` |  |
| adminConfig.DB_SERVER | string | `""` | leave empty if uses Mongo DB deployed by this chart |
| adminConfig.JWTSecret | string | `"litmus-portal@123"` |  |
| adminConfig.VERSION | string | `"2.3.0"` |  |
| customLabels | object | `{}` | Additional labels |
| image.imagePullSecrets[0].name | string | `"regcred"` |  |
| image.imageRegistryName | string | `"chaosnative"` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.host.name | string | `""` | This is ingress hostname (ex: my-domain.com) |
| ingress.host.paths.backend | string | `"/backend/(.*)"` | You may need adapt the path depending your ingress-controller |
| ingress.host.paths.frontend | string | `"/(.*)"` | You may need adapt the path depending your ingress-controller |
| ingress.name | string | `"litmus-ingress"` |  |
| ingress.tls | list | `[]` |  |
| mongo.affinity | object | `{}` |  |
| mongo.containerPort | int | `27017` |  |
| mongo.customLabels | object | `{}` |  |
| mongo.image.pullPolicy | string | `"Always"` |  |
| mongo.image.repository | string | `"mongo"` |  |
| mongo.image.tag | string | `"4.2.8"` |  |
| mongo.livenessProbe.failureThreshold | int | `5` |  |
| mongo.livenessProbe.initialDelaySeconds | int | `30` |  |
| mongo.livenessProbe.periodSeconds | int | `10` |  |
| mongo.livenessProbe.successThreshold | int | `1` |  |
| mongo.livenessProbe.timeoutSeconds | int | `5` |  |
| mongo.nodeSelector | object | `{}` |  |
| mongo.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| mongo.persistence.size | string | `"20Gi"` |  |
| mongo.readinessProbe.initialDelaySeconds | int | `5` |  |
| mongo.readinessProbe.periodSeconds | int | `10` |  |
| mongo.readinessProbe.successThreshold | int | `1` |  |
| mongo.readinessProbe.timeoutSeconds | int | `1` |  |
| mongo.replicas | int | `1` |  |
| mongo.resources | object | `{}` |  |
| mongo.service.port | int | `27017` |  |
| mongo.service.targetPort | int | `27017` |  |
| mongo.service.type | string | `"ClusterIP"` |  |
| mongo.tolerations | list | `[]` |  |
| nameOverride | string | `""` |  |
| openshift.route.annotations | object | `{}` |  |
| openshift.route.enabled | bool | `false` |  |
| openshift.route.host | string | `""` |  |
| openshift.route.name | string | `"litmus-portal"` |  |
| portal.frontend.affinity | object | `{}` |  |
| portal.frontend.containerPort | int | `8080` |  |
| portal.frontend.customLabels | object | `{}` |  |
| portal.frontend.image.pullPolicy | string | `"Always"` |  |
| portal.frontend.image.repository | string | `"cle-frontend"` |  |
| portal.frontend.image.tag | string | `"2.3.0"` |  |
| portal.frontend.livenessProbe.failureThreshold | int | `5` |  |
| portal.frontend.livenessProbe.initialDelaySeconds | int | `30` |  |
| portal.frontend.livenessProbe.periodSeconds | int | `10` |  |
| portal.frontend.livenessProbe.successThreshold | int | `1` |  |
| portal.frontend.livenessProbe.timeoutSeconds | int | `5` |  |
| portal.frontend.nodeSelector | object | `{}` |  |
| portal.frontend.readinessProbe.initialDelaySeconds | int | `5` |  |
| portal.frontend.readinessProbe.periodSeconds | int | `10` |  |
| portal.frontend.readinessProbe.successThreshold | int | `1` |  |
| portal.frontend.readinessProbe.timeoutSeconds | int | `1` |  |
| portal.frontend.replicas | int | `1` |  |
| portal.frontend.resources | object | `{}` |  |
| portal.frontend.service.port | int | `9091` |  |
| portal.frontend.service.targetPort | int | `8080` |  |
| portal.frontend.service.type | string | `"NodePort"` |  |
| portal.frontend.tolerations | list | `[]` |  |
| portal.frontend.updateStrategy | object | `{}` |  |
| portal.frontend.virtualService.enabled | bool | `false` |  |
| portal.frontend.virtualService.gateways | list | `[]` |  |
| portal.frontend.virtualService.hosts | list | `[]` |  |
| portal.server.affinity | object | `{}` |  |
| portal.server.authServer.containerPort | int | `3000` |  |
| portal.server.authServer.env.ADMIN_PASSWORD | string | `"litmus"` |  |
| portal.server.authServer.env.ADMIN_USERNAME | string | `"admin"` |  |
| portal.server.authServer.image.pullPolicy | string | `"Always"` |  |
| portal.server.authServer.image.repository | string | `"cle-auth-server"` |  |
| portal.server.authServer.image.tag | string | `"2.3.0"` |  |
| portal.server.authServer.resources | object | `{}` |  |
| portal.server.customLabels | object | `{}` |  |
| portal.server.graphqlServer.containerPort | int | `8080` |  |
| portal.server.graphqlServer.genericEnv.AGENT_DEPLOYMENTS | string | `"[\"app=chaos-exporter\", \"name=chaos-operator\", \"app=event-tracker\", \"app=workflow-controller\"]"` |  |
| portal.server.graphqlServer.genericEnv.CONTAINER_RUNTIME_EXECUTOR | string | `"k8sapi"` |  |
| portal.server.graphqlServer.genericEnv.EVENT_TRACKER_IMAGE | string | `"chaosnative/cle-event-tracker:2.3.0"` |  |
| portal.server.graphqlServer.genericEnv.HUB_BRANCH_NAME | string | `"v2.2.x"` |  |
| portal.server.graphqlServer.genericEnv.SELF_CLUSTER | string | `"true"` |  |
| portal.server.graphqlServer.genericEnv.SUBSCRIBER_IMAGE | string | `"chaosnative/cle-subscriber:2.3.0"` |  |
| portal.server.graphqlServer.image.pullPolicy | string | `"Always"` |  |
| portal.server.graphqlServer.image.repository | string | `"cle-server"` |  |
| portal.server.graphqlServer.image.tag | string | `"2.3.0"` |  |
| portal.server.graphqlServer.imageEnv.ARGO_WORKFLOW_CONTROLLER_IMAGE | string | `"litmuschaos/workflow-controller:v2.11.0"` |  |
| portal.server.graphqlServer.imageEnv.ARGO_WORKFLOW_EXECUTOR_IMAGE | string | `"litmuschaos/argoexec:v2.11.0"` |  |
| portal.server.graphqlServer.imageEnv.LITMUS_CHAOS_EXPORTER_IMAGE | string | `"litmuschaos/chaos-exporter:2.3.0"` |  |
| portal.server.graphqlServer.imageEnv.LITMUS_CHAOS_OPERATOR_IMAGE | string | `"litmuschaos/chaos-operator:2.3.0"` |  |
| portal.server.graphqlServer.imageEnv.LITMUS_CHAOS_RUNNER_IMAGE | string | `"litmuschaos/chaos-runner:2.3.0"` |  |
| portal.server.graphqlServer.livenessProbe.failureThreshold | int | `5` |  |
| portal.server.graphqlServer.livenessProbe.initialDelaySeconds | int | `30` |  |
| portal.server.graphqlServer.livenessProbe.periodSeconds | int | `10` |  |
| portal.server.graphqlServer.livenessProbe.successThreshold | int | `1` |  |
| portal.server.graphqlServer.livenessProbe.timeoutSeconds | int | `5` |  |
| portal.server.graphqlServer.readinessProbe.initialDelaySeconds | int | `5` |  |
| portal.server.graphqlServer.readinessProbe.periodSeconds | int | `10` |  |
| portal.server.graphqlServer.readinessProbe.successThreshold | int | `1` |  |
| portal.server.graphqlServer.readinessProbe.timeoutSeconds | int | `1` |  |
| portal.server.graphqlServer.resources | object | `{}` |  |
| portal.server.licenseServer.containerPort | int | `8080` |  |
| portal.server.licenseServer.image.pullPolicy | string | `"Always"` |  |
| portal.server.licenseServer.image.repository | string | `"cle-license-module"` |  |
| portal.server.licenseServer.image.tag | string | `"2.3.0"` |  |
| portal.server.licenseServer.service.port | int | `80` |  |
| portal.server.licenseServer.service.targetPort | int | `8080` |  |
| portal.server.licenseServer.service.type | string | `"ClusterIP"` |  |
| portal.server.nodeSelector | object | `{}` |  |
| portal.server.replicas | int | `1` |  |
| portal.server.serverVersionUpdater.image.pullPolicy | string | `"Always"` |  |
| portal.server.serverVersionUpdater.image.repository | string | `"mongo-utils"` |  |
| portal.server.serverVersionUpdater.image.tag | string | `"latest"` |  |
| portal.server.service.authServer.port | int | `9003` |  |
| portal.server.service.authServer.targetPort | int | `3000` |  |
| portal.server.service.graphqlServer.port | int | `9002` |  |
| portal.server.service.graphqlServer.targetPort | int | `8080` |  |
| portal.server.service.type | string | `"NodePort"` |  |
| portal.server.serviceAccountName | string | `"litmus-server-account"` |  |
| portal.server.tolerations | list | `[]` |  |
| portal.server.updateStrategy | object | `{}` |  |
| portal.server.waitForMongodb.image.pullPolicy | string | `"Always"` |  |
| portal.server.waitForMongodb.image.repository | string | `"curl"` |  |
| portal.server.waitForMongodb.image.tag | string | `"latest"` |  |
| portalScope | string | `"cluster"` |  |
| upgradeAgent.affinity | object | `{}` |  |
| upgradeAgent.controlPlane.image.pullPolicy | string | `"Always"` |  |
| upgradeAgent.controlPlane.image.repository | string | `"upgrade-agent-cp"` |  |
| upgradeAgent.controlPlane.image.tag | string | `"ci"` |  |
| upgradeAgent.nodeSelector | object | `{}` |  |
| upgradeAgent.tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.6.0](https://github.com/norwoodj/helm-docs/releases/v1.6.0)
