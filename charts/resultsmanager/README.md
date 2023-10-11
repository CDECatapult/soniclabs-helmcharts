# ResultsManager

## Parameters

### ResultsManager Parameters

| Name                       | Description                                                             | Value            |
| -------------------------- | ----------------------------------------------------------------------- | ---------------- |
| `config.replicaCount`      | The amount of containers to run                                         | `1`              |
| `config.type`              | The type of service to create                                           | `LoadBalancer`   |
| `config.appPort`           | The port to expose the service and application on                       | `8000`           |
| `config.nodePort`          | The nodePort to use if the the service type is LoadBalancer or NodePort | `30342`          |
| `config.commonAnnotations` | The annotations to set on the Results Manager application               | `{}`             |
| `config.debug`             | Whether or not to enable debug mode for the application                 | `False`          |
| `config.logLevel`          | The log level to use for the application                                | `DEBUG`          |
| `config.gui.host`          | The hostname of the GUI service                                         | `portal`         |
| `config.gui.port`          | The port of the GUI service                                             | `8000`           |
| `config.sma.host`          | The hostname of the Suite Manager service                               | `suitemanager`   |
| `config.sma.port`          | The port of the Suite Manager service                                   | `8000`           |
| `config.tma.host`          | The hostname of the Test Manager service                                | `testmanager`    |
| `config.tma.port`          | The port of the Test Manager service                                    | `8000`           |
| `config.rma.host`          | The hostname of the Results Manager service                             | `resultsmanager` |
| `config.rma.port`          | The port of the Results Manager service                                 | `8000`           |
| `config.apg.host`          | The hostname of the API Gateway service                                 | `apigateway`     |
| `config.apg.port`          | The port of the API Gateway service                                     | `8000`           |
| `config.dma.host`          | The hostname of the Deploy Manager service                              | `deploymanager`  |
| `config.dma.port`          | The port of the Deploy Manager service                                  | `8000`           |

### ResultsManager Image Parameters

| Name                | Description                                           | Value                                          |
| ------------------- | ----------------------------------------------------- | ---------------------------------------------- |
| `image.repository`  | The repository to use for the Results Manager image   | `ghcr.io/cdecatapult/soniclabs-resultsmanager` |
| `image.pullPolicy`  | The pull policy to use for the Results Manager image  | `Always`                                       |
| `image.tag`         | The tag to use for the Results Manager image          | `v1.1.0`                                       |
| `image.pullSecrets` | The pull secrets to use for the Results Manager image | `["soniclabs"]`                                |

### ResultsManager Ingress parameters

| Name                        | Description                                                               | Value                  |
| --------------------------- | ------------------------------------------------------------------------- | ---------------------- |
| `ingress.enabled`           | Whether or not to enable the ingress for the Results Manager application  | `true`                 |
| `ingress.annotations`       | The annotations to set on the ingress for the Results Manager application | `{}`                   |
| `ingress.ingressClassName`  | The ingress class to use for the Results Manager application              | `""`                   |
| `ingress.hostname`          | The hostname to use for the Results Manager application                   | `resultsmanager.local` |
| `ingress.paths`             | The paths to use for the Results Manager application                      |                        |
| `ingress.paths[0].path`     | The path to use for the Results Manager application                       | `/api/rma`             |
| `ingress.paths[0].pathType` | The path type to use for the Results Manager application                  | `Prefix`               |

### ResultsManager ServiceAccount parameters

| Name                         | Description                                                                | Value   |
| ---------------------------- | -------------------------------------------------------------------------- | ------- |
| `serviceAccount.create`      | Whether or not to create a service account for the Results Manager service | `false` |
| `serviceAccount.annotations` | The annotations to use for the Results Manager service account             | `{}`    |
| `serviceAccount.name`        | The name of the service account to use for the Results Manager service     | `""`    |

### ResultsManager PostgreSQL parameters

| Name                                          | Description                                                                      | Value            |
| --------------------------------------------- | -------------------------------------------------------------------------------- | ---------------- |
| `postgresql.enabled`                          | Whether or not to enable the PostgreSQL SubChart for the Results Manager service | `true`           |
| `postgresql.primary.service.ports.postgresql` | The port to expose the PostgreSQL database service on                            | `5432`           |
| `postgresql.auth.username`                    | The username to use for the PostgreSQL database                                  | `tamuser`        |
| `postgresql.auth.password`                    | The password to use for the PostgreSQL database                                  | `tampassword`    |
| `postgresql.auth.database`                    | The name of the database to use for the PostgreSQL database                      | `resultsmanager` |
