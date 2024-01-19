# Part-2
Docker Containers with Commands

# Step 1 & 2
ubuntu@ip-172-31-40-168:~/images/app$ docker run -d --name appwebsite -p 9080:80 appimg:v4
c4e0c94ee8758e3f21eff4e61b5464125a4c0b4cc628f9853b98b0dc9ed792e1
ubuntu@ip-172-31-40-168:~/images/app$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED         STATUS         PORTS                                   NAMES
c4e0c94ee875   appimg:v4   "/usr/sbin/apache2ct…"   4 seconds ago   Up 3 seconds   0.0.0.0:9080->80/tcp, :::9080->80/tcp   appwebsite

  
# Step 3
■ 'docker ps' command to list all running containers
CONTAINER ID   IMAGE       COMMAND                  CREATED         STATUS         PORTS                                   NAMES
c4e0c94ee875   appimg:v4   "/usr/sbin/apache2ct…"   4 seconds ago   Up 3 seconds   0.0.0.0:9080->80/tcp, :::9080->80/tcp   appwebsite


■ 'docker stop' command to stop a running container
ubuntu@ip-172-31-40-168:~/images/app$ docker stop c4e0c94ee875
c4e0c94ee875
ubuntu@ip-172-31-40-168:~/images/app$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
ubuntu@ip-172-31-40-168:~/images/app$ docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED         STATUS                        PORTS     NAMES
c4e0c94ee875   appimg:v4     "/usr/sbin/apache2ct…"   6 minutes ago   Exited (137) 13 seconds ago             appwebsite
40dd4ed3ba97   hello-world   "/hello" 

■ 'docker rm' command to remove a stopped container
ubuntu@ip-172-31-40-168:~/images/app$ docker rm c4e0c94ee875
c4e0c94ee875
ubuntu@ip-172-31-40-168:~/images/app$ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED       STATUS                   PORTS     NAMES
40dd4ed3ba97   hello-world   "/hello"   5 hours ago   Exited (0) 5 hours ago             elastic_mclean
ubuntu@ip-172-31-40-168:~/images/app$


■ 'docker logs' command to view the logs of a container
ubuntu@ip-172-31-40-168:~/images/app$ docker logs c64ac248c192
AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 172.17.0.2. Set the 'ServerName' directive globally to suppress this message


■ 'docker inspect' command to view the details of a container
  ubuntu@ip-172-31-40-168:~/images/app$ docker inspect c64ac248c192
[
    {
        "Id": "c64ac248c19223817405145c389629a54f92e2a6429fba70cba6af25fbb80568",
        "Created": "2024-01-19T16:19:11.341906027Z",
        "Path": "/usr/sbin/apache2ctl",
        "Args": [
            "-D",
            "FOREGROUND"
        ],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 1757,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2024-01-19T16:19:11.769130093Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:883741f8c352b7c3a292fb2be171af64c5f6437d056cfc35fca5bd93d8fcc190",
        "ResolvConfPath": "/var/lib/docker/containers/c64ac248c19223817405145c389629a54f92e2a6429fba70cba6af25fbb80568/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/c64ac248c19223817405145c389629a54f92e2a6429fba70cba6af25fbb80568/hostname",
        "HostsPath": "/var/lib/docker/containers/c64ac248c19223817405145c389629a54f92e2a6429fba70cba6af25fbb80568/hosts",
        "LogPath": "/var/lib/docker/containers/c64ac248c19223817405145c389629a54f92e2a6429fba70cba6af25fbb80568/c64ac248c19223817405145c389629a54f92e2a6429fba70cba6af25fbb80568-json.log",
        "Name": "/appwebsite",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "docker-default",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {
                "80/tcp": [
                    {
                        "HostIp": "",
                        "HostPort": "9080"
                    }
                ]
            },
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "ConsoleSize": [
                43,
                145
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
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
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
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/1b3fc1753c8ee78970f35303e8f12aa7fef790d48ded996626886def50e67ef5-init/diff:/var/lib/docker/overlay2/km1135zp54fpq6kwexk5nx9b9/diff:/var/lib/docker/overlay2/s8k4r1tv1gpwpzw6uz47ok44j/diff:/var/lib/docker/overlay2/xu2zc94l5tqk8ipfur9c0o9jv/diff:/var/lib/docker/overlay2/86rsftb180scuauvzj4ch4ief/diff:/var/lib/docker/overlay2/7d1a4a66f073be375b99157dde343289456b67541e0bc7af93942d610a34bc27/diff",
                "MergedDir": "/var/lib/docker/overlay2/1b3fc1753c8ee78970f35303e8f12aa7fef790d48ded996626886def50e67ef5/merged",
                "UpperDir": "/var/lib/docker/overlay2/1b3fc1753c8ee78970f35303e8f12aa7fef790d48ded996626886def50e67ef5/diff",
                "WorkDir": "/var/lib/docker/overlay2/1b3fc1753c8ee78970f35303e8f12aa7fef790d48ded996626886def50e67ef5/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [
            {
                "Type": "volume",
                "Name": "d29bc13cbf28a014f2037fd97dc08909c3e373b73fe1770894ad640d99c9e059",
                "Source": "/var/lib/docker/volumes/d29bc13cbf28a014f2037fd97dc08909c3e373b73fe1770894ad640d99c9e059/_data",
                "Destination": "/var/log/apache2",
                "Driver": "local",
                "Mode": "",
                "RW": true,
                "Propagation": ""
            }
        ],
        "Config": {
            "Hostname": "c64ac248c192",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "DEBIAN_FRONTEND=noninteractive"
            ],
            "Cmd": [
                "/usr/sbin/apache2ctl",
                "-D",
                "FOREGROUND"
            ],
            "Image": "appimg:v2",
            "Volumes": {
                "/var/log/apache2": {}
            },
            "WorkingDir": "/var/www/html",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {
                "Author": "Attia",
                "Project": "app",
                "org.opencontainers.image.ref.name": "ubuntu",
                "org.opencontainers.image.version": "22.04"
            }
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "4f8e1773ad3183d60c5527907c2ede93ff23fc444120cd37850f8ab57968f44c",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "80/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "9080"
                    },
                    {
                        "HostIp": "::",
                        "HostPort": "9080"
                    }
                ]
            },
            "SandboxKey": "/var/run/docker/netns/4f8e1773ad31",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "f4c434faaf332992aad9895cf6943e83487cf2a57563d22abc5804ed26e5298d",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "5cf7e2ec8c057aace826d51cef17e612614bc0e2a1041337cfd675e910dd7a94",
                    "EndpointID": "f4c434faaf332992aad9895cf6943e83487cf2a57563d22abc5804ed26e5298d",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]
  
    

■ 'docker exec' command to execute a command inside a running container
ubuntu@ip-172-31-40-168:~/images/app$ docker exec -it c64ac248c192 bash
root@c64ac248c192:/var/www/html# ls
'ABOUT THIS TEMPLATE.txt'   coming-soon.html   css     images       js              services-detail.html
 about.html                 contact.html       fonts   index.html   page-404.html   services.html
root@c64ac248c192:/var/www/html#  


■ 'docker commit' command to create a new image from a container
ubuntu@ip-172-31-40-168:~$ docker commit c64ac248c192 aaleem1993/ubuntunew
sha256:080fdbdf77daeaa8a1949f5b95c2ef1554ee4bcd78091618e1c6b208f858500e


■ 'docker stats' command to view the resource usage of containers
ubuntu@ip-172-31-40-168:~$ docker stats c64ac248c192
CONTAINER ID   NAME         CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O         PIDS
c64ac248c192   appwebsite   0.01%     7.012MiB / 949.7MiB   0.74%     1.37kB / 0B   2.06MB / 12.3kB   56
CONTAINER ID   NAME         CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O         PIDS
c64ac248c192   appwebsite   0.01%     7.012MiB / 949.7MiB   0.74%     1.37kB / 0B   2.06MB / 12.3kB   56
CONTAINER ID   NAME         CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O         PIDS
c64ac248c192   appwebsite   0.01%     7.012MiB / 949.7MiB   0.74%     1.37kB / 0B   2.06MB / 12.3kB   56
CONTAINER ID   NAME         CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O         PIDS


■ 'docker top' command to view the running processes inside a container
  ubuntu@ip-172-31-40-168:~$ docker top c64ac248c192
UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                1757                1734                0                   16:19               ?                   00:00:00            /bin/sh /usr/sbin/apache2ctl -D FOREGROUND
root                1788                1757                0                   16:19               ?                   00:00:00            /usr/sbin/apache2 -D FOREGROUND
www-data            1789                1788                0                   16:19               ?                   00:00:00            /usr/sbin/apache2 -D FOREGROUND
www-data            1790                1788                0                   16:19               ?                   00:00:00            /usr/sbin/apache2 -D FOREGROUND


■ 'docker start' command to start a stopped container
ubuntu@ip-172-31-40-168:~$ docker stop c64ac248c192
c64ac248c192
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
ubuntu@ip-172-31-40-168:~$ docker start c64ac248c192
c64ac248c192
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED             STATUS         PORTS                                   NAMES
c64ac248c192   appimg:v2   "/usr/sbin/apache2ct…"   About an hour ago   Up 4 seconds   0.0.0.0:9080->80/tcp, :::9080->80/tcp   appwebsite


■ 'docker pause' command to pause a running container
ubuntu@ip-172-31-40-168:~$ docker pause c64ac248c192
c64ac248c192
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED             STATUS                      PORTS                                   NAMES
c64ac248c192   appimg:v2   "/usr/sbin/apache2ct…"   About an hour ago   Up About an hour (Paused)   0.0.0.0:9080->80/tcp, :::9080->80/tcp   appwebsite

■ 'docker unpause' command to unpause a paused container
 ubuntu@ip-172-31-40-168:~$ docker unpause c64ac248c192
c64ac248c192
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED             STATUS             PORTS                                   NAMES
c64ac248c192   appimg:v2   "/usr/sbin/apache2ct…"   About an hour ago   Up About an hour   0.0.0.0:9080->80/tcp, :::9080->80/tcp   appwebsite


■ 'docker rename' command to rename a container
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED             STATUS              PORTS                                   NAMES
c64ac248c192   appimg:v2   "/usr/sbin/apache2ct…"   About an hour ago   Up About a minute   0.0.0.0:9080->80/tcp, :::9080->80/tcp   appwebsite
ubuntu@ip-172-31-40-168:~$ docker rename c64ac248c192 newappd
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED             STATUS         PORTS                                   NAMES
c64ac248c192   appimg:v2   "/usr/sbin/apache2ct…"   About an hour ago   Up 2 minutes   0.0.0.0:9080->80/tcp, :::9080->80/tcp   newappd


■ 'docker wait' command to wait for a container to exit and then display its
exit code
ubuntu@ip-172-31-40-168:~$ docker container wait c64ac248c192
0
ubuntu@ip-172-31-40-168:~$


■ 'docker port' command to display the public-facing port that a container is
listening on
ubuntu@ip-172-31-40-168:~$ docker port c64ac248c192
80/tcp -> 0.0.0.0:9080
80/tcp -> [::]:9080

■ 'docker update' command to update a container's resource limits
ubuntu@ip-172-31-40-168:~$  docker update --cpu-shares 512 c64ac248c192
c64ac248c192

■ 'docker restart' command to restart a running container
ubuntu@ip-172-31-40-168:~$ docker restart c64ac248c192
c64ac248c192
ubuntu@ip-172-31-40-168:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED       STATUS         PORTS                                   NAMES
c64ac248c192   appimg:v2   "/usr/sbin/apache2ct…"   2 hours ago   Up 4 seconds   0.0.0.0:9080->80/tcp, :::9080->80/tcp   newappd
ubuntu@ip-172-31-40-168:~$






