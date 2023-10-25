# SonicLabs Portal

## Parameters

### Portal Parameters

| Name                       | Description                                                             | Value            |
| -------------------------- | ----------------------------------------------------------------------- | ---------------- |
| `config.replicaCount`      | The amount of containers to run                                         | `1`              |
| `config.type`              | The type of service to create                                           | `LoadBalancer`   |
| `config.appPort`           | The port to expose the service and application on                       | `80`             |
| `config.nodePort`          | The nodePort to use if the the service type is LoadBalancer or NodePort | `30342`          |
| `config.commonAnnotations` | The annotations to set on the Portal application                        | `{}`             |
| `config.cma.host`          | The hostname of the Config Manager service                              | `configmanager`  |
| `config.cma.port`          | The port of the Config Manager service                                  | `8000`           |
| `config.sma.host`          | The hostname of the Suite Manager service                               | `suitemanager`   |
| `config.sma.port`          | The port of the Suite Manager service                                   | `8000`           |
| `config.tma.host`          | The hostname of the Test Manager service                                | `testmanager`    |
| `config.tma.port`          | The port of the Test Manager service                                    | `8000`           |
| `config.rma.host`          | The hostname of the Results Manager service                             | `resultsmanager` |
| `config.rma.port`          | The port of the Results Manager service                                 | `8000`           |
| `config.dma.host`          | The hostname of the Deploy Manager service                              | `deploymanager`  |
| `config.dma.port`          | The port of the Deploy Manager service                                  | `8000`           |

### ConfigManager Image Parameters

| Name                | Description                                  | Value                                  |
| ------------------- | -------------------------------------------- | -------------------------------------- |
| `image.repository`  | The repository to use for the Portal image   | `ghcr.io/cdecatapult/soniclabs-portal` |
| `image.pullPolicy`  | The pull policy to use for the Portal image  | `Always`                               |
| `image.tag`         | The tag to use for the Portal image          | `v0.0.7`                               |
| `image.pullSecrets` | The pull secrets to use for the Portal image | `["soniclabs"]`                        |

### Portal Ingress parameters

| Name                        | Description                                                      | Value          |
| --------------------------- | ---------------------------------------------------------------- | -------------- |
| `ingress.enabled`           | Whether or not to enable the ingress for the Portal application  | `true`         |
| `ingress.annotations`       | The annotations to set on the ingress for the Portal application | `{}`           |
| `ingress.ingressClassName`  | The ingress class to use for the Portal application              | `""`           |
| `ingress.hostname`          | The hostname to use for the Portal application                   | `portal.local` |
| `ingress.paths`             | The paths to use for the Portal application                      |                |
| `ingress.paths[0].path`     | The path to use for the Portal application                       | `/`            |
| `ingress.paths[0].pathType` | The path type to use for the Portal application                  | `Prefix`       |

### Portal ServiceAccount parameters

| Name                         | Description                                                       | Value   |
| ---------------------------- | ----------------------------------------------------------------- | ------- |
| `serviceAccount.create`      | Whether or not to create a service account for the Portal service | `false` |
| `serviceAccount.annotations` | The annotations to use for the Portal service account             | `{}`    |
| `serviceAccount.name`        | The name of the service account to use for the Portal service     | `""`    |
