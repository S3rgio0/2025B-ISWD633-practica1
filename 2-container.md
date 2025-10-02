# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
# COMPLETAR
<img width="527" height="75" alt="imagen" src="https://github.com/user-attachments/assets/05a7a5fe-3047-4f30-b98c-613c70808bf2" />

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
# COMPLETAR
<img width="677" height="175" alt="imagen" src="https://github.com/user-attachments/assets/70ec44a1-d9ea-4b2d-b221-b247fad8553e" />

### Listar los contenedores ejecutándose o no
<img width="662" height="192" alt="imagen" src="https://github.com/user-attachments/assets/c6537411-2764-413c-a3f1-90a0d239f435" />

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
# COMPLETAR
<img width="622" height="79" alt="imagen" src="https://github.com/user-attachments/assets/a8074f89-70bd-4c39-b051-a05deaec931e" />

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
# COMPLETAR
<img width="1271" height="699" alt="imagen" src="https://github.com/user-attachments/assets/bd7e7538-960d-420a-b1a1-14bb7933c3b7" />

**¿Qué sucede luego de la ejecución del comando?**
# COMPLETAR  
Se ejecuta el contenedor en primer plano, se captura la entrada estandar de la terminal

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
# COMPLETAR
<img width="636" height="129" alt="imagen" src="https://github.com/user-attachments/assets/c67b0d8a-0df7-4288-b997-5bf39ed4f4bc" />

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
# COMPLETAR
<img width="435" height="91" alt="imagen" src="https://github.com/user-attachments/assets/cfd3845b-78c0-4b16-baff-1a0dbf509e9c" />

Verificar que el contenedor que se eliminó
# COMPLETAR
<img width="961" height="147" alt="imagen" src="https://github.com/user-attachments/assets/45753ff8-e899-46f3-8a3c-83ea046b8c24" />

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
# COMPLETAR
<img width="341" height="82" alt="imagen" src="https://github.com/user-attachments/assets/1c44fa35-00bb-4bfb-8b6f-464c9f16cfe9" />

Verificar que el contenedor que se eliminó
# COMPLETAR
<img width="953" height="129" alt="imagen" src="https://github.com/user-attachments/assets/2005bd47-4ee8-4522-b298-38a1db215c46" />

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
# COMPLETAR
```
C:\Users\LabP4E001>docker inspect srv-web
[
    {
        "Id": "8adae66b1136724a3fabc089e22a6daee186672ad1a9f2e5ba6449cbcf5e1482",
        "Created": "2025-10-02T22:06:58.972647629Z",
        "Path": "/docker-entrypoint.sh",
        "Args": [
            "nginx",
            "-g",
            "daemon off;"
        ],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 586,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2025-10-02T22:13:54.510400435Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:42a516af16b852e33b7682d5ef8acbd5d13fe08fecadc7ed98605ba5e3b26ab8",
        "ResolvConfPath": "/var/lib/docker/containers/8adae66b1136724a3fabc089e22a6daee186672ad1a9f2e5ba6449cbcf5e1482/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/8adae66b1136724a3fabc089e22a6daee186672ad1a9f2e5ba6449cbcf5e1482/hostname",
        "HostsPath": "/var/lib/docker/containers/8adae66b1136724a3fabc089e22a6daee186672ad1a9f2e5ba6449cbcf5e1482/hosts",
        "LogPath": "/var/lib/docker/containers/8adae66b1136724a3fabc089e22a6daee186672ad1a9f2e5ba6449cbcf5e1482/8adae66b1136724a3fabc089e22a6daee186672ad1a9f2e5ba6449cbcf5e1482-json.log",
        "Name": "/srv-web",
        "RestartCount": 0,
        "Driver": "overlayfs",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "bridge",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "ConsoleSize": [
                51,
                82
            ],
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "private",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": [],
            "BlkioDeviceWriteBps": [],
            "BlkioDeviceReadIOps": [],
            "BlkioDeviceWriteIOps": [],
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": null,
            "PidsLimit": null,
            "Ulimits": [],
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/interrupts",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware",
                "/sys/devices/virtual/powercap"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": null,
            "Name": "overlayfs"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "8adae66b1136",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": true,
            "AttachStderr": true,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "NGINX_VERSION=1.29.1",
                "PKG_RELEASE=1",
                "DYNPKG_RELEASE=1",
                "NJS_VERSION=0.9.1",
                "NJS_RELEASE=1"
            ],
            "Cmd": [
                "nginx",
                "-g",
                "daemon off;"
            ],
            "Image": "nginx:alpine",
            "Volumes": null,
            "WorkingDir": "/",
            "Entrypoint": [
                "/docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NGINX Docker Maintainers \u003cdocker-maint@nginx.com\u003e"
            },
            "StopSignal": "SIGQUIT"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "c995d9f392a7496549367521a6855283520ec31443fbd8d82140621589746839",
            "SandboxKey": "/var/run/docker/netns/c995d9f392a7",
            "Ports": {
                "80/tcp": null
            },
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "dd44b317511990eb76dda80126d223fe6c05d0724414d07c2db2833288936a18",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "a2:ec:6a:dc:52:37",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "MacAddress": "a2:ec:6a:dc:52:37",
                    "DriverOpts": null,
                    "GwPriority": 0,
                    "NetworkID": "334a1c72c03cf7551703234df0f6660291b96f23082df46ebaea088f0eb4897f",
                    "EndpointID": "dd44b317511990eb76dda80126d223fe6c05d0724414d07c2db2833288936a18",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "DNSNames": null
                }
            }
        },
        "ImageManifestDescriptor": {
            "mediaType": "application/vnd.oci.image.manifest.v1+json",
            "digest": "sha256:60e48a050b6408d0c5dd59b98b6e36bf0937a0bbe99304e3e9c0e63b7563443a",
            "size": 2495,
            "annotations": {
                "com.docker.official-images.bashbrew.arch": "amd64",
                "org.opencontainers.image.base.digest": "sha256:94f11b88c5d30105df2236d818a2dd50577bd2314f70374ae53ccaec61ac34f0",
                "org.opencontainers.image.base.name": "nginx:1.29.1-alpine-slim",
                "org.opencontainers.image.created": "2025-08-13T18:57:48Z",
                "org.opencontainers.image.revision": "5a4ad48c733b365d69a4d1c9946a9d8480469c7f",
                "org.opencontainers.image.source": "https://github.com/nginx/docker-nginx.git#5a4ad48c733b365d69a4d1c9946a9d8480469c7f:mainline/alpine",
                "org.opencontainers.image.url": "https://hub.docker.com/_/nginx",
                "org.opencontainers.image.version": "1.29.1-alpine"
            },
            "platform": {
                "architecture": "amd64",
                "os": "linux"
            }
        }
    }
]
```
