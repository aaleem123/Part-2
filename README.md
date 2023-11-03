# Part-2
Docker Containers with Commands

# Step 1
root@ubuntu-focal:~/myapp# docker images
REPOSITORY    TAG       IMAGE ID       CREATED          SIZE
myapp         latest    4b222ea4d311   12 seconds ago   187MB

# Step 2
root@ubuntu-focal:~/myapp# docker run -d -p 8080:80 myapp
505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8
yes, I can access my app. 
  
# Step 3
■ 'docker ps' command to list all running containers
  CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                   NAMES
505cc2fcd247   myapp     "/docker-entrypoint.…"   16 seconds ago   Up 14 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   loving_babbage

■ 'docker stop' command to stop a running container
  root@ubuntu-focal:~# docker stop ecdd88acc367
ecdd88acc367

■ 'docker rm' command to remove a stopped container
  root@ubuntu-focal:~# docker rm 505cc2fcd247
505cc2fcd247

■ 'docker logs' command to view the logs of a container
    root@ubuntu-focal:~/myapp# docker logs 505cc2fcd247
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/11/03 13:41:53 [notice] 1#1: using the "epoll" event method
2023/11/03 13:41:53 [notice] 1#1: nginx/1.25.3
2023/11/03 13:41:53 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14)
2023/11/03 13:41:53 [notice] 1#1: OS: Linux 5.4.0-164-generic
2023/11/03 13:41:53 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/11/03 13:41:53 [notice] 1#1: start worker processes
2023/11/03 13:41:53 [notice] 1#1: start worker process 29
2023/11/03 13:41:53 [notice] 1#1: start worker process 30

■ 'docker inspect' command to view the details of a container
      [
    {
        "Id": "505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8",
        "Created": "2023-11-03T13:41:52.357713751Z",
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
            "Pid": 9209,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2023-11-03T13:41:53.542614276Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:4b222ea4d311f69a4882aa9350689dbfd26e961f342ee67c827aeb401d0654c1",
        "ResolvConfPath": "/var/lib/docker/containers/505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8/hostname",
        "HostsPath": "/var/lib/docker/containers/505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8/hosts",
        "LogPath": "/var/lib/docker/containers/505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8/505cc2fcd247791cc7573408deaf25a95f3d6cb9d0da7f1512a3315f767e15e8-json.log",
        "Name": "/loving_babbage",
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
                        "HostPort": "8080"
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
                51,
                109
            ],
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
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
            "OomKillDisable": false,
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
                "LowerDir": "/var/lib/docker/overlay2/672520513ab1df3f9dad880cabb94e4b3d12a2dfc26b388ce67db70b470db294-init/diff:/var/lib/docker/overlay2/xftm78fdn1c1c7oc0iz73epr6/diff:/var/lib/docker/overlay2/27b8c9ee3826ee78ed374e35e56c51301472490bae90cdff1b61f08e7b6ba78a/diff:/var/lib/docker/overlay2/257f77fc319a587f8dbc55e476c2ecad763b3014ffe28ba75ead6c063197a12c/diff:/var/lib/docker/overlay2/03873dc8d7cd8b215f2c4057e5bf6dcf31cd3e1aca49f9b0c01b604ab2035a43/diff:/var/lib/docker/overlay2/e99bef1ea68c734d8de6d6c9857b481ab22814d9af28e989b85efe3fcbd528fd/diff:/var/lib/docker/overlay2/7154344b13ccd4616c15da36a6ace23c9f8f65e36bf0fe6003fa31c63c94158d/diff:/var/lib/docker/overlay2/876e747579adc498f81f2d82706a3696b5f1179e93488bc3086a3670ea65fa2e/diff:/var/lib/docker/overlay2/b46af251a00945d6c27006c75daf53cd62d56abc6e068fcb7170c630d8b6a60e/diff",
                "MergedDir": "/var/lib/docker/overlay2/672520513ab1df3f9dad880cabb94e4b3d12a2dfc26b388ce67db70b470db294/merged",
                "UpperDir": "/var/lib/docker/overlay2/672520513ab1df3f9dad880cabb94e4b3d12a2dfc26b388ce67db70b470db294/diff",
                "WorkDir": "/var/lib/docker/overlay2/672520513ab1df3f9dad880cabb94e4b3d12a2dfc26b388ce67db70b470db294/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "505cc2fcd247",
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
                "NGINX_VERSION=1.25.3",
                "NJS_VERSION=0.8.2",
                "PKG_RELEASE=1~bookworm"
            ],
            "Cmd": [
                "nginx",
                "-g",
                "daemon off;"
            ],
            "Image": "myapp",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "/docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NGINX Docker Maintainers <docker-maint@nginx.com>"
            },
            "StopSignal": "SIGQUIT"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "c534a42906ad203153c1b5aff268e792c1e19beb0dcdd73f34ef0e2730ba3ae2",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "80/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "8080"
                    },
                    {
                        "HostIp": "::",
                        "HostPort": "8080"
                    }
                ]
            },
            "SandboxKey": "/var/run/docker/netns/c534a42906ad",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "577616341a27c41a4080f96d57b3c34fca4c09c787cf2cb35d020c22c2927eb0",
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
                    "NetworkID": "2a60dbdf79a19bb42f6c67549fbb1ff975a252ed12e021d266273e778ed2a5b4",
                    "EndpointID": "577616341a27c41a4080f96d57b3c34fca4c09c787cf2cb35d020c22c2927eb0",
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
  root@ubuntu-focal:~/myapp# docker exec -it 505cc2fcd247 /bin/bash
  root@505cc2fcd247:/#
  
■ 'docker attach' command to attach to a running container
  root@ubuntu-focal:~# docker attach 505cc2fcd247
2023/11/03 15:42:53 [notice] 1#1: signal 28 (SIGWINCH) received
2023/11/03 15:42:53 [notice] 1#1: signal 28 (SIGWINCH) received
2023/11/03 15:42:53 [notice] 1#1: signal 28 (SIGWINCH) received
2023/11/03 15:47:56 [notice] 1#1: signal 28 (SIGWINCH) received
2023/11/03 15:47:56 [notice] 1#1: signal 28 (SIGWINCH) received
2023/11/03 15:47:56 [notice] 1#1: signal 28 (SIGWINCH) received

■ 'docker commit' command to create a new image from a container
  root@ubuntu-focal:~# docker commit 505cc2fcd247 aaleem1993/newapp:v1.0
sha256:54893332d45b43bf9a5d778cbd14e92aa55685febe6336cf7aa53f3dff21cb06

■ 'docker cp' command to copy files/folders between the container and the
host
  root@ubuntu-focal:~# docker cp afile.txt  5e0841c4e023:/tmp
  Successfully copied 1.54kB to 5e0841c4e023:/tmp

■ 'docker stats' command to view the resource usage of containers
CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT   MEM %     NET I/O   BLOCK I/O   PIDS

■ 'docker top' command to view the running processes inside a container
  root@ubuntu-focal:~# docker top d3101abf5817
  UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
  root                10857               10831               0                   16:28               ?                   00:00:00            nginx: master process nginx -g daemon off;
  systemd+            10906               10857               0                   16:28               ?                   00:00:00            nginx: worker process
  systemd+            10907               10857               0                   16:28               ?                   00:00:00            nginx: worker process

■ 'docker start' command to start a stopped container
  root@ubuntu-focal:~# docker start d3101abf5817
d3101abf5817

■ 'docker pause' command to pause a running container
  root@ubuntu-focal:~# docker pause d3101abf5817
  d3101abf5817

■ 'docker unpause' command to unpause a paused container
  root@ubuntu-focal:~# docker unpause d3101abf5817
d3101abf5817

■ 'docker rename' command to rename a container
root@ubuntu-focal:~# docker rename d3101abf5817 freshapp
root@ubuntu-focal:~# docker ps -a
d3101abf5817   myapp         "/docker-entrypoint.…"   18 minutes ago   Up 18 minutes             0.0.0.0:8080->80/tcp, :::8080->80/tcp   freshapp

■ 'docker port' command to display the public-facing port that a container is
listening on
  root@ubuntu-focal:~# docker port d3101abf5817
  80/tcp -> 0.0.0.0:8080
  80/tcp -> [::]:8080





