# TestManager

## Parameters

### TestManager Parameters

| Name                                  | Description                                                             | Value                                                                            |
| ------------------------------------- |-------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| `config.replicaCount`                 | The amount of containers to run                                         | `1`                                                                              |
| `config.type`                         | The type of service to create                                           | `LoadBalancer`                                                                   |
| `config.appPort`                      | The port to expose the service and application on                       | `8000`                                                                           |
| `config.nodePort`                     | The nodePort to use if the the service type is LoadBalancer or NodePort | `30342`                                                                          |
| `config.commonAnnotations`            | The annotations to set on the Test Manager application                  | `{}`                                                                             |
| `config.debug`                        | Whether or not to enable debug mode for the application                 | `False`                                                                          |
| `config.logLevel`                     | The log level to use for the application                                | `debug`                                                                          |
| `config.rtcPort`                      | The port of the Viavi RTC                                               | `5099`                                                                           |
| `config.tmaPath`                      | The path on the "Control Host" to use to execute the TMA.               | `C:/Program Files (x86)/VIAVI/TM500/5G NR - NLA 6.16.0/Test Mobile Application/` |
| `config.sshKey`                       | The SSH key to use for accessing ORAN components                        | `blahblah                                                                        
| `config.protocolsFilePath`            | The location of the protocols file that is generated.                   | `./`                                                                             |
blahblahblah
blahblahblahblah
`                                        |
| `config.pcapStorage.accessMode`       | The access mode to use for the PCAP storage PVC                         | `ReadWriteMany`                                                                  |
| `config.pcapStorage.path`             | The path to use for the PCAP storage PVC                                | `/mnt/pcaps`                                                                     |
| `config.pcapStorage.size`             | The size to use for the PCAP storage PVC                                | `10Gi`                                                                           |
| `config.pcapStorage.storageClassName` | The storage class to use for the PCAP storage PVC                       | `azurefile`                                                                      |
| `config.gui.host`                     | The hostname of the GUI service                                         | `portal`                                                                         |
| `config.gui.port`                     | The port of the GUI service                                             | `8000`                                                                           |
| `config.sma.host`                     | The hostname of the Suite Manager service                               | `suitemanager`                                                                   |
| `config.sma.port`                     | The port of the Suite Manager service                                   | `8000`                                                                           |
| `config.cma.host`                     | The hostname of the Config Manager service                              | `configmanager`                                                                  |
| `config.cma.port`                     | The port of the Config Manager service                                  | `8000`                                                                           |
| `config.rma.host`                     | The hostname of the Results Manager service                             | `resultsmanager`                                                                 |
| `config.rma.port`                     | The port of the Results Manager service                                 | `8000`                                                                           |
| `config.apg.host`                     | The hostname of the API Gateway service                                 | `apigateway`                                                                     |
| `config.apg.port`                     | The port of the API Gateway service                                     | `8000`                                                                           |
| `config.dma.host`                     | The hostname of the Deploy Manager service                              | `deploymanager`                                                                  |
| `config.dma.port`                     | The port of the Deploy Manager service                                  | `8000`                                                                           |
| `config.controlHost`                  | The hostname for the the Control TMA Host                               | `example`                                                                        |
| `config.controlShare`                 | The name of the Samba Sharename on the Control TMA Host                 | `Public`                                                                         |
| `config.controlUsername`              | The username to use for the Control TMA Host                            | `username`                                                                       |
| `config.controlPassword`              | The password to use for the Control TMA Host                            | `password`                                                                       |

### TestManager Image Parameters

| Name                | Description                                        | Value                                          |
| ------------------- | -------------------------------------------------- | ---------------------------------------------- |
| `image.repository`  | The repository to use for the Test Manager image   | `ghcr.io/cdecatapult/soniclabs-testmanager-ts` |
| `image.pullPolicy`  | The pull policy to use for the Test Manager image  | `Always`                                       |
| `image.tag`         | The tag to use for the Test Manager image          | `v0.3.6`                                       |
| `image.pullSecrets` | The pull secrets to use for the Test Manager image | `["soniclabs"]`                                |

### TestManager Ingress parameters

| Name                        | Description                                                            | Value      |
| --------------------------- | ---------------------------------------------------------------------- | ---------- |
| `ingress.enabled`           | Whether or not to enable the ingress for the Test Manager application  | `true`     |
| `ingress.annotations`       | The annotations to set on the ingress for the Test Manager application | `{}`       |
| `ingress.ingressClassName`  | The ingress class to use for the Test Manager application              | `""`       |
| `ingress.hostname`          | The hostname to use for the Test Manager application                   | `""`       |
| `ingress.paths`             | The paths to use for the Test Manager application                      |            |
| `ingress.paths[0].path`     | The path to use for IoT tests in the Test Manager application          | `/api/tma` |
| `ingress.paths[0].pathType` | The path type to use for Iot tests in the Test Manager application     | `Prefix`   |

### TestManager ServiceAccount parameters

| Name                         | Description                                                             | Value   |
| ---------------------------- | ----------------------------------------------------------------------- | ------- |
| `serviceAccount.create`      | Whether or not to create a service account for the Test Manager service | `false` |
| `serviceAccount.annotations` | The annotations to use for the Test Manager service account             | `{}`    |
| `serviceAccount.name`        | The name of the service account to use for the Test Manager service     | `""`    |

### TestManager PostgreSQL parameters

| Name                                          | Description                                                                   | Value         |
| --------------------------------------------- | ----------------------------------------------------------------------------- | ------------- |
| `postgresql.enabled`                          | Whether or not to enable the PostgreSQL SubChart for the Test Manager service | `true`        |
| `postgresql.primary.service.ports.postgresql` | The port to expose the PostgreSQL database service on                         | `5432`        |
| `postgresql.auth.username`                    | The username to use for the PostgreSQL database                               | `tamuser`     |
| `postgresql.auth.password`                    | The password to use for the PostgreSQL database                               | `tampassword` |
| `postgresql.auth.database`                    | The name of the database to use for the PostgreSQL database                   | `testmanager` |
