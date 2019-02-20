Docker commands

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

PS C:\WINDOWS\system32> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
PS C:\WINDOWS\system32> docker images
REPOSITORY                                 TAG                 IMAGE ID            CREATED             SIZE
k8s.gcr.io/kube-proxy-amd64                v1.10.11            7387003276ac        2 months ago        98.3MB
k8s.gcr.io/kube-apiserver-amd64            v1.10.11            e851a7aeb6e8        2 months ago        228MB
k8s.gcr.io/kube-controller-manager-amd64   v1.10.11            978cfa2028bf        2 months ago        151MB
k8s.gcr.io/kube-scheduler-amd64            v1.10.11            d2c751d562c6        2 months ago        51.2MB
docker/kube-compose-controller             v0.4.12             02a45592fbea        4 months ago        27.8MB
docker/kube-compose-api-server             v0.4.12             0f92c77fa676        4 months ago        41.2MB
k8s.gcr.io/etcd-amd64                      3.1.12              52920ad46f5b        11 months ago       193MB
k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     1.14.8              c2ce1ffb51ed        13 months ago       41MB
k8s.gcr.io/k8s-dns-sidecar-amd64           1.14.8              6f7f2dc7fab5        13 months ago       42.2MB
k8s.gcr.io/k8s-dns-kube-dns-amd64          1.14.8              80cc5ea4b547        13 months ago       50.5MB
k8s.gcr.io/pause-amd64                     3.1                 da86e6ba6ca1        14 months ago       742kB
PS C:\WINDOWS\system32> docker version
Client: Docker Engine - Community
 Version:           18.09.2
 API version:       1.39
 Go version:        go1.10.8
 Git commit:        6247962
 Built:             Sun Feb 10 04:12:31 2019
 OS/Arch:           windows/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          18.09.2
  API version:      1.39 (minimum version 1.12)
  Go version:       go1.10.6
  Git commit:       6247962
  Built:            Sun Feb 10 04:13:06 2019
  OS/Arch:          linux/amd64
  Experimental:     false
 Kubernetes:
  Version:          v1.10.11
  StackAPI:         v1beta2
PS C:\WINDOWS\system32> docker info
Containers: 18
 Running: 18
 Paused: 0
 Stopped: 0
Images: 11
Server Version: 18.09.2
Storage Driver: overlay2
 Backing Filesystem: extfs
 Supports d_type: true
 Native Overlay Diff: true
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: bridge host macvlan null overlay
 Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
Swarm: inactive
Runtimes: runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 9754871865f7fe2f4e74d43e2fc7ccd237edcbce
runc version: 09c8266bf2fcf9519a651b04ae54c967b9ab86ec
init version: fec3683
Security Options:
 seccomp
  Profile: default
Kernel Version: 4.9.125-linuxkit
Operating System: Docker for Windows
OSType: linux
Architecture: x86_64
CPUs: 2
Total Memory: 1.934GiB
Name: linuxkit-00155d630101
ID: GCVR:I6HD:L33Y:YZEK:ZWYS:36WK:7CNV:J5OJ:SWDI:OB5T:HEZN:DZK3
Docker Root Dir: /var/lib/docker
Debug Mode (client): false
Debug Mode (server): true
 File Descriptors: 119
 Goroutines: 123
 System Time: 2019-02-17T08:43:02.2392039Z
 EventsListeners: 1
Registry: https://index.docker.io/v1/
Labels:
Experimental: false
Insecure Registries:
 127.0.0.0/8
Live Restore Enabled: false
Product License: Community Engine

PS C:\WINDOWS\system32> docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:2557e3c07ed1e38f26e389462d03ed943586f744621577a99efb77324b0fe535
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

PS C:\WINDOWS\system32> docker ps
CONTAINER ID        IMAGE                                      COMMAND                  CREATED             STATUS              PORTS               NAMES
b461e6e45e54        docker/kube-compose-controller             "/compose-controller…"   2 minutes ago       Up 2 minutes                            k8s_compose_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
d6647652deda        docker/kube-compose-api-server             "/api-server --kubec…"   3 minutes ago       Up 3 minutes                            k8s_compose_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
a35c2b15c4a1        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 3 minutes ago       Up 3 minutes                            k8s_POD_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
37f539f33404        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 3 minutes ago       Up 3 minutes                            k8s_POD_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
5e8d9d738d9f        k8s.gcr.io/k8s-dns-sidecar-amd64           "/sidecar --v=2 --lo…"   3 minutes ago       Up 3 minutes                            k8s_sidecar_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
08b8bd5395d1        k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     "/dnsmasq-nanny -v=2…"   3 minutes ago       Up 3 minutes                            k8s_dnsmasq_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
0c86e831b156        k8s.gcr.io/k8s-dns-kube-dns-amd64          "/kube-dns --domain=…"   3 minutes ago       Up 3 minutes                            k8s_kubedns_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
e97e982b30a6        k8s.gcr.io/kube-proxy-amd64                "/usr/local/bin/kube…"   3 minutes ago       Up 3 minutes                            k8s_kube-proxy_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
428cfe930997        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 4 minutes ago       Up 4 minutes                            k8s_POD_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
e394eef59d88        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 4 minutes ago       Up 4 minutes                            k8s_POD_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
8d0182b17303        k8s.gcr.io/kube-controller-manager-amd64   "kube-controller-man…"   4 minutes ago       Up 4 minutes                            k8s_kube-controller-manager_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
f16217866b58        k8s.gcr.io/kube-apiserver-amd64            "kube-apiserver --ad…"   4 minutes ago       Up 4 minutes                            k8s_kube-apiserver_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
349021798f15        k8s.gcr.io/kube-scheduler-amd64            "kube-scheduler --ad…"   5 minutes ago       Up 5 minutes                            k8s_kube-scheduler_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
a9e45fb19f90        k8s.gcr.io/etcd-amd64                      "etcd --peer-client-…"   5 minutes ago       Up 5 minutes                            k8s_etcd_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
9d51112dfcb4        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 5 minutes ago       Up 5 minutes                            k8s_POD_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
5584baa34484        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 5 minutes ago       Up 5 minutes                            k8s_POD_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
b345c49068bf        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 5 minutes ago       Up 5 minutes                            k8s_POD_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
3645bfda966f        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 5 minutes ago       Up 5 minutes                            k8s_POD_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
PS C:\WINDOWS\system32> docker kill hello-world
Error response from daemon: Cannot kill container: hello-world: No such container: hello-world
PS C:\WINDOWS\system32> docker images
REPOSITORY                                 TAG                 IMAGE ID            CREATED             SIZE
hello-world                                latest              fce289e99eb9        6 weeks ago         1.84kB
k8s.gcr.io/kube-proxy-amd64                v1.10.11            7387003276ac        2 months ago        98.3MB
k8s.gcr.io/kube-apiserver-amd64            v1.10.11            e851a7aeb6e8        2 months ago        228MB
k8s.gcr.io/kube-controller-manager-amd64   v1.10.11            978cfa2028bf        2 months ago        151MB
k8s.gcr.io/kube-scheduler-amd64            v1.10.11            d2c751d562c6        2 months ago        51.2MB
docker/kube-compose-controller             v0.4.12             02a45592fbea        4 months ago        27.8MB
docker/kube-compose-api-server             v0.4.12             0f92c77fa676        4 months ago        41.2MB
k8s.gcr.io/etcd-amd64                      3.1.12              52920ad46f5b        11 months ago       193MB
k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     1.14.8              c2ce1ffb51ed        13 months ago       41MB
k8s.gcr.io/k8s-dns-sidecar-amd64           1.14.8              6f7f2dc7fab5        13 months ago       42.2MB
k8s.gcr.io/k8s-dns-kube-dns-amd64          1.14.8              80cc5ea4b547        13 months ago       50.5MB
k8s.gcr.io/pause-amd64                     3.1                 da86e6ba6ca1        14 months ago       742kB
PS C:\WINDOWS\system32> docker stop hello-world
Error response from daemon: No such container: hello-world
PS C:\WINDOWS\system32> docker ps
CONTAINER ID        IMAGE                                      COMMAND                  CREATED             STATUS              PORTS               NAMES
b461e6e45e54        docker/kube-compose-controller             "/compose-controller…"   4 minutes ago       Up 4 minutes                            k8s_compose_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
d6647652deda        docker/kube-compose-api-server             "/api-server --kubec…"   4 minutes ago       Up 4 minutes                            k8s_compose_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
a35c2b15c4a1        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 5 minutes ago       Up 5 minutes                            k8s_POD_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
37f539f33404        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 5 minutes ago       Up 5 minutes                            k8s_POD_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
5e8d9d738d9f        k8s.gcr.io/k8s-dns-sidecar-amd64           "/sidecar --v=2 --lo…"   5 minutes ago       Up 5 minutes                            k8s_sidecar_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
08b8bd5395d1        k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     "/dnsmasq-nanny -v=2…"   5 minutes ago       Up 5 minutes                            k8s_dnsmasq_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
0c86e831b156        k8s.gcr.io/k8s-dns-kube-dns-amd64          "/kube-dns --domain=…"   5 minutes ago       Up 5 minutes                            k8s_kubedns_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
e97e982b30a6        k8s.gcr.io/kube-proxy-amd64                "/usr/local/bin/kube…"   5 minutes ago       Up 5 minutes                            k8s_kube-proxy_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
428cfe930997        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 6 minutes                            k8s_POD_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
e394eef59d88        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 6 minutes                            k8s_POD_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
8d0182b17303        k8s.gcr.io/kube-controller-manager-amd64   "kube-controller-man…"   6 minutes ago       Up 6 minutes                            k8s_kube-controller-manager_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
f16217866b58        k8s.gcr.io/kube-apiserver-amd64            "kube-apiserver --ad…"   6 minutes ago       Up 6 minutes                            k8s_kube-apiserver_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
349021798f15        k8s.gcr.io/kube-scheduler-amd64            "kube-scheduler --ad…"   7 minutes ago       Up 7 minutes                            k8s_kube-scheduler_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
a9e45fb19f90        k8s.gcr.io/etcd-amd64                      "etcd --peer-client-…"   7 minutes ago       Up 7 minutes                            k8s_etcd_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
9d51112dfcb4        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 7 minutes ago       Up 7 minutes                            k8s_POD_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
5584baa34484        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 7 minutes ago       Up 7 minutes                            k8s_POD_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
b345c49068bf        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 7 minutes ago       Up 7 minutes                            k8s_POD_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
3645bfda966f        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 7 minutes ago       Up 7 minutes                            k8s_POD_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
PS C:\WINDOWS\system32>














































PS C:\WINDOWS\system32> docker ps
CONTAINER ID        IMAGE                                      COMMAND                  CREATED             STATUS              PORTS               NAMES
b461e6e45e54        docker/kube-compose-controller             "/compose-controller…"   5 minutes ago       Up 5 minutes                            k8s_compose_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
d6647652deda        docker/kube-compose-api-server             "/api-server --kubec…"   5 minutes ago       Up 5 minutes                            k8s_compose_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
a35c2b15c4a1        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 5 minutes                            k8s_POD_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
37f539f33404        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 5 minutes                            k8s_POD_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
5e8d9d738d9f        k8s.gcr.io/k8s-dns-sidecar-amd64           "/sidecar --v=2 --lo…"   6 minutes ago       Up 6 minutes                            k8s_sidecar_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
08b8bd5395d1        k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     "/dnsmasq-nanny -v=2…"   6 minutes ago       Up 6 minutes                            k8s_dnsmasq_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
0c86e831b156        k8s.gcr.io/k8s-dns-kube-dns-amd64          "/kube-dns --domain=…"   6 minutes ago       Up 6 minutes                            k8s_kubedns_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
e97e982b30a6        k8s.gcr.io/kube-proxy-amd64                "/usr/local/bin/kube…"   6 minutes ago       Up 6 minutes                            k8s_kube-proxy_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
428cfe930997        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 6 minutes                            k8s_POD_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
e394eef59d88        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 6 minutes                            k8s_POD_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
8d0182b17303        k8s.gcr.io/kube-controller-manager-amd64   "kube-controller-man…"   7 minutes ago       Up 7 minutes                            k8s_kube-controller-manager_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
f16217866b58        k8s.gcr.io/kube-apiserver-amd64            "kube-apiserver --ad…"   7 minutes ago       Up 7 minutes                            k8s_kube-apiserver_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
349021798f15        k8s.gcr.io/kube-scheduler-amd64            "kube-scheduler --ad…"   7 minutes ago       Up 7 minutes                            k8s_kube-scheduler_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
a9e45fb19f90        k8s.gcr.io/etcd-amd64                      "etcd --peer-client-…"   7 minutes ago       Up 7 minutes                            k8s_etcd_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
9d51112dfcb4        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                            k8s_POD_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
5584baa34484        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                            k8s_POD_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
b345c49068bf        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                            k8s_POD_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
3645bfda966f        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                            k8s_POD_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
PS C:\WINDOWS\system32> docker images
REPOSITORY                                 TAG                 IMAGE ID            CREATED             SIZE
hello-world                                latest              fce289e99eb9        6 weeks ago         1.84kB
k8s.gcr.io/kube-proxy-amd64                v1.10.11            7387003276ac        2 months ago        98.3MB
k8s.gcr.io/kube-apiserver-amd64            v1.10.11            e851a7aeb6e8        2 months ago        228MB
k8s.gcr.io/kube-controller-manager-amd64   v1.10.11            978cfa2028bf        2 months ago        151MB
k8s.gcr.io/kube-scheduler-amd64            v1.10.11            d2c751d562c6        2 months ago        51.2MB
docker/kube-compose-controller             v0.4.12             02a45592fbea        4 months ago        27.8MB
docker/kube-compose-api-server             v0.4.12             0f92c77fa676        4 months ago        41.2MB
k8s.gcr.io/etcd-amd64                      3.1.12              52920ad46f5b        11 months ago       193MB
k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     1.14.8              c2ce1ffb51ed        13 months ago       41MB
k8s.gcr.io/k8s-dns-sidecar-amd64           1.14.8              6f7f2dc7fab5        13 months ago       42.2MB
k8s.gcr.io/k8s-dns-kube-dns-amd64          1.14.8              80cc5ea4b547        13 months ago       50.5MB
k8s.gcr.io/pause-amd64                     3.1                 da86e6ba6ca1        14 months ago       742kB
PS C:\WINDOWS\system32> docker stop hello-world
Error response from daemon: No such container: hello-world
PS C:\WINDOWS\system32> docker ps -a
CONTAINER ID        IMAGE                                      COMMAND                  CREATED             STATUS                     PORTS               NAMES
c3b508a57010        hello-world                                "/hello"                 3 minutes ago       Exited (0) 3 minutes ago                       objective_bhabha
b461e6e45e54        docker/kube-compose-controller             "/compose-controller…"   6 minutes ago       Up 6 minutes                                   k8s_compose_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
d6647652deda        docker/kube-compose-api-server             "/api-server --kubec…"   6 minutes ago       Up 6 minutes                                   k8s_compose_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
a35c2b15c4a1        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 6 minutes                                   k8s_POD_compose-74649b4db6-bdbz7_docker_9f756b30-328f-11e9-bf0b-00155d630101_0
37f539f33404        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 6 minutes ago       Up 6 minutes                                   k8s_POD_compose-api-5b85fcb8b5-ww2rv_docker_9ea30ae1-328f-11e9-bf0b-00155d630101_0
5e8d9d738d9f        k8s.gcr.io/k8s-dns-sidecar-amd64           "/sidecar --v=2 --lo…"   6 minutes ago       Up 6 minutes                                   k8s_sidecar_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
08b8bd5395d1        k8s.gcr.io/k8s-dns-dnsmasq-nanny-amd64     "/dnsmasq-nanny -v=2…"   6 minutes ago       Up 6 minutes                                   k8s_dnsmasq_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
0c86e831b156        k8s.gcr.io/k8s-dns-kube-dns-amd64          "/kube-dns --domain=…"   6 minutes ago       Up 6 minutes                                   k8s_kubedns_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
e97e982b30a6        k8s.gcr.io/kube-proxy-amd64                "/usr/local/bin/kube…"   7 minutes ago       Up 7 minutes                                   k8s_kube-proxy_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
428cfe930997        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 7 minutes ago       Up 7 minutes                                   k8s_POD_kube-proxy-mlc96_kube-system_7d1991a1-328f-11e9-bf0b-00155d630101_0
e394eef59d88        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 7 minutes ago       Up 7 minutes                                   k8s_POD_kube-dns-86f4d74b45-d7kxp_kube-system_7ce0bf9c-328f-11e9-bf0b-00155d630101_0
8d0182b17303        k8s.gcr.io/kube-controller-manager-amd64   "kube-controller-man…"   7 minutes ago       Up 7 minutes                                   k8s_kube-controller-manager_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
f16217866b58        k8s.gcr.io/kube-apiserver-amd64            "kube-apiserver --ad…"   8 minutes ago       Up 8 minutes                                   k8s_kube-apiserver_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
349021798f15        k8s.gcr.io/kube-scheduler-amd64            "kube-scheduler --ad…"   8 minutes ago       Up 8 minutes                                   k8s_kube-scheduler_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
a9e45fb19f90        k8s.gcr.io/etcd-amd64                      "etcd --peer-client-…"   8 minutes ago       Up 8 minutes                                   k8s_etcd_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
9d51112dfcb4        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                                   k8s_POD_kube-controller-manager-docker-for-desktop_kube-system_236923a37e5a87d68533ea188802a3fe_0
5584baa34484        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                                   k8s_POD_kube-scheduler-docker-for-desktop_kube-system_b6155a27330304c86badfef38a6b483b_0
b345c49068bf        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                                   k8s_POD_kube-apiserver-docker-for-desktop_kube-system_d5c8a3ec1a14cd7936b621dd696c337a_0
3645bfda966f        k8s.gcr.io/pause-amd64:3.1                 "/pause"                 8 minutes ago       Up 8 minutes                                   k8s_POD_etcd-docker-for-desktop_kube-system_48a894d028bbc51f058e1cfc9c0a4ee4_0
PS C:\WINDOWS\system32> cd..
PS C:\WINDOWS> cd..
PS C:\> dir


    Directory: C:\


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       23/08/2018     20:08                Archivos de programa
d-----       23/05/2018     20:37                BIOS
d-----       17/02/2019     07:44                BuildAgent
d-----       15/01/2019     20:07                Desk
d-----       13/01/2017     17:29                fonts
d-----       21/05/2018     01:23                inetpub
d-----       02/04/2018     17:00                Logs
d-----       21/09/2016     22:11                NDepend
d-----       12/04/2018     00:38                PerfLogs
da----       17/02/2019     08:07                PNotes.NET
d-r---       15/02/2019     19:02                Program Files
d-r---       16/02/2019     19:03                Program Files (x86)
d-----       30/03/2018     15:54                Python34
d-----       02/07/2016     16:18                remote
d-----       25/11/2018     19:00                shared
d-----       06/08/2016     10:56                SSH
d-----       21/11/2016     21:05                Symbols
d-----       25/11/2018     19:42                temp
d-----       25/06/2016     10:00                totalcmd
d-r---       20/05/2018     17:21                Users
d-----       17/02/2019     07:42                Windows
-a----       13/02/2019     19:20       83723776 kubectl.exe
-a----       13/02/2019     19:21       39061504 minikube.exe
-a----       01/12/2006     22:37         904704 msdia80.dll


PS C:\> .\minikube.exe version
minikube version: v0.33.1
PS C:\> .\minikube get-k8s-versions
Error: unknown command "get-k8s-versions" for "minikube"
Run 'minikube --help' for usage.
PS C:\> .\minikube start
There is a newer version of minikube available (v0.34.1).  Download it here:
https://github.com/kubernetes/minikube/releases/tag/v0.34.1

To disable this notification, run the following:
minikube config set WantUpdateNotification false
Starting local Kubernetes v1.13.2 cluster...
Starting VM...
E0217 16:54:58.181177   23580 start.go:205] Error starting host: Error starting stopped host: Unable to start the VM: C:\Program Files\Oracle\VirtualBox\VBoxManage.exe startvm minikube --type headless failed:
VBoxManage.exe: error: The virtual machine 'minikube' has terminated unexpectedly during startup with exit code 1 (0x1).  More details may be available in 'C:\Users\thund\.minikube\machines\minikube\minikube\Logs\VBoxHardening.log'
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component MachineWrap, interface IMachine
.

 Retrying.
E0217 16:54:58.183155   23580 start.go:211] Error starting host:  Error starting stopped host: Unable to start the VM: C:\Program Files\Oracle\VirtualBox\VBoxManage.exe startvm minikube --type headless failed:
VBoxManage.exe: error: The virtual machine 'minikube' has terminated unexpectedly during startup with exit code 1 (0x1).  More details may be available in 'C:\Users\thund\.minikube\machines\minikube\minikube\Logs\VBoxHardening.log'
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component MachineWrap, interface IMachine

================================================================================
An error has occurred. Would you like to opt in to sending anonymized crash
information to minikube to help prevent future errors?

To disable this prompt, run: 'minikube config set WantReportErrorPrompt false'
================================================================================
Please enter your response [Y/n]: Prompt timed out.
Bummer, perhaps next time!


minikube failed :( exiting with error code 1
PS C:\> Get-NetAdapter

Name                      InterfaceDescription                    ifIndex Status       MacAddress             LinkSpeed
----                      --------------------                    ------- ------       ----------             ---------
vEthernet (DockerNAT)     Hyper-V Virtual Ethernet Adapter #2          69 Up           00-15-5D-63-01-00        10 Gbps
Wi-Fi                     Intel(R) Dual Band Wireless-AC 3160          22 Up           78-0C-B8-0C-2B-14     292.5 Mbps
HMA! Pro VPN              HMA TAP-Windows Adapter V9                   21 Up           00-FF-C9-83-A7-D3       100 Mbps
Ethernet                  Realtek PCIe GBE Family Controller           15 Disconnected 1C-39-47-18-C2-82          0 bps
VirtualBox Host-Only ...2 VirtualBox Host-Only Ethernet Adap...#2       7 Up           0A-00-27-00-00-07         1 Gbps
vEthernet (Default Swi... Hyper-V Virtual Ethernet Adapter              4 Up           96-15-ED-5E-FD-22        10 Gbps


PS C:\> New-VMSwitch –Name "minikube" –AllowManagement $True –NetAdapterName "Wi-Fi"

Name     SwitchType NetAdapterInterfaceDescription
----     ---------- ------------------------------
minikube External   Intel(R) Dual Band Wireless-AC 3160


PS C:\> minikube start --vm-driver=hyperv --hyperv-virtual-switch=minikube
minikube : The term 'minikube' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ minikube start --vm-driver=hyperv --hyperv-virtual-switch=minikube
+ ~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (minikube:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


Suggestion [3,General]: The command minikube was not found, but does exist in the current location. Windows PowerShell does not load commands from the current location by default. If you trust this command, instead type: ".\minikube". See "get-help about_Command_Precedence" for more details.
PS C:\> .\minikube start --vm-driver=hyperv --hyperv-virtual-switch=minikube
Starting local Kubernetes v1.13.2 cluster...
Starting VM...
Skipping hyperv driver, existing host has virtualbox driver.
E0217 17:30:32.888387    1560 start.go:205] Error starting host: Error starting stopped host: Unable to start the VM: C:\Program Files\Oracle\VirtualBox\VBoxManage.exe startvm minikube --type headless failed:
VBoxManage.exe: error: The virtual machine 'minikube' has terminated unexpectedly during startup with exit code 1 (0x1).  More details may be available in 'C:\Users\thund\.minikube\machines\minikube\minikube\Logs\VBoxHardening.log'
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component MachineWrap, interface IMachine
.

 Retrying.
E0217 17:30:32.890370    1560 start.go:211] Error starting host:  Error starting stopped host: Unable to start the VM: C:\Program Files\Oracle\VirtualBox\VBoxManage.exe startvm minikube --type headless failed:
VBoxManage.exe: error: The virtual machine 'minikube' has terminated unexpectedly during startup with exit code 1 (0x1).  More details may be available in 'C:\Users\thund\.minikube\machines\minikube\minikube\Logs\VBoxHardening.log'
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component MachineWrap, interface IMachine

================================================================================
An error has occurred. Would you like to opt in to sending anonymized crash
information to minikube to help prevent future errors?

To disable this prompt, run: 'minikube config set WantReportErrorPrompt false'
================================================================================
Please enter your response [Y/n]: Prompt timed out.
Bummer, perhaps next time!


minikube failed :( exiting with error code 1
PS C:\> .\minikube delete
Deleting local Kubernetes cluster...
Machine deleted.
PS C:\> .\minikube start --vm-driver=hyperv --hyperv-virtual-switch=minikube --v=7 --alsologtostderr
W0217 17:31:32.536333    9648 root.go:146] Error reading config file at C:\Users\thund\.minikube\config\config.json: open C:\Users\thund\.minikube\config\config.json: The system cannot find the file specified.
Starting local Kubernetes v1.13.2 cluster...
Starting VM...
I0217 17:31:32.542349    9648 cluster.go:69] Machine does not exist... provisioning new machine
I0217 17:31:32.542349    9648 cluster.go:70] Provisioning machine with config: {MinikubeISO:https://storage.googleapis.com/minikube/iso/minikube-v0.33.1.iso Memory:2048 CPUs:2 DiskSize:20000 VMDriver:hyperv ContainerRuntime: HyperkitVpnKitSock: HyperkitVSockPorts:[] XhyveDiskDriver:ahci-hd DockerEnv:[] InsecureRegistry:[] RegistryMirror:[] HostOnlyCIDR:192.168.99.1/24 HypervVirtualSwitch:minikube KvmNetwork:default Downloader:{} DockerOpt:[] DisableDriverMounts:false NFSShare:[] NFSSharesRoot:/nfsshares UUID: GPU:false}
I0217 17:31:32.544333    9648 downloader.go:56] Not caching ISO, using https://storage.googleapis.com/minikube/iso/minikube-v0.33.1.iso
Reading certificate data from C:\Users\thund\.minikube\certs\ca.pem
Decoding PEM data...
Parsing certificate...
Reading certificate data from C:\Users\thund\.minikube\certs\cert.pem
Decoding PEM data...
Parsing certificate...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive @(Get-Module -ListAvailable hyper-v).Name | Get-Unique
[stdout =====>] : Hyper-V

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive @([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole("S-1-5-32-578")
[stdout =====>] : False

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive @([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole] "Administrator")
[stdout =====>] : True

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (Hyper-V\Get-VMSwitch).Name
[stdout =====>] : Default Switch
DockerNAT
minikube

[stderr =====>] :
Downloading C:\Users\thund\.minikube\cache\boot2docker.iso from file://C:/Users/thund/.minikube/cache/iso/minikube-v0.33.1.iso...
Creating SSH key...
Creating VM...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (Hyper-V\Get-VMSwitch).Name
[stdout =====>] : Default Switch
DockerNAT
minikube

[stderr =====>] :
Using switch "minikube"
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive @([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole] "Administrator")
[stdout =====>] : True

[stderr =====>] :
Creating VHD
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\New-VHD -Path 'C:\Users\thund\.minikube\machines\minikube\fixed.vhd' -SizeBytes 10MB -Fixed
[stdout =====>] :

ComputerName            : LAPTOP-NB3QKBHM
Path                    : C:\Users\thund\.minikube\machines\minikube\fixed.vhd
VhdFormat               : VHD
VhdType                 : Fixed
FileSize                : 10486272
Size                    : 10485760
MinimumSize             :
LogicalSectorSize       : 512
PhysicalSectorSize      : 512
BlockSize               : 0
ParentPath              :
DiskIdentifier          : 7699454E-7919-4E59-A804-9E150D1F54F3
FragmentationPercentage : 0
Alignment               : 1
Attached                : False
DiskNumber              :
IsPMEMCompatible        : False
AddressAbstractionType  : None
Number                  :




[stderr =====>] :
Writing magic tar header
Writing SSH key tar header
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Convert-VHD -Path 'C:\Users\thund\.minikube\machines\minikube\fixed.vhd' -DestinationPath 'C:\Users\thund\.minikube\machines\minikube\disk.vhd' -VHDType Dynamic -DeleteSource
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Resize-VHD -Path 'C:\Users\thund\.minikube\machines\minikube\disk.vhd' -SizeBytes 20000MB
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\New-VM minikube -Path 'C:\Users\thund\.minikube\machines\minikube' -SwitchName 'minikube' -MemoryStartupBytes 2048MB
[stdout =====>] :
Name     State CPUUsage(%) MemoryAssigned(M) Uptime   Status             Version
----     ----- ----------- ----------------- ------   ------             -------
minikube Off   0           0                 00:00:00 Operating normally 8.3



[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Set-VMProcessor minikube -Count 2
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Set-VMDvdDrive -VMName minikube -Path 'C:\Users\thund\.minikube\machines\minikube\boot2docker.iso'
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Add-VMHardDiskDrive -VMName minikube -Path 'C:\Users\thund\.minikube\machines\minikube\disk.vhd'
[stdout =====>] :
[stderr =====>] :
Starting VM...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Start-VM minikube
[stdout =====>] :
[stderr =====>] :
Waiting for host to start...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] :
[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
setting hostname "minikube"
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo hostname minikube && echo "minikube" | sudo tee /etc/hostname
Error dialing TCP: ssh: handshake failed: ssh: unable to authenticate, attempted methods [none publickey], no supported methods remain
SSH cmd err, output: <nil>: minikube

[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:

                if ! grep -xq '.*\sminikube' /etc/hosts; then
                        if grep -xq '127.0.1.1\s.*' /etc/hosts; then
                                sudo sed -i 's/^127.0.1.1\s.*/127.0.1.1 minikube/g' /etc/hosts;
                        else
                                echo '127.0.1.1 minikube' | sudo tee -a /etc/hosts;
                        fi
                fi
SSH cmd err, output: <nil>:
set auth options {CertDir:C:\Users\thund\.minikube CaCertPath:C:\Users\thund\.minikube\certs\ca.pem CaPrivateKeyPath:C:\Users\thund\.minikube\certs\ca-key.pem CaCertRemotePath:/etc/docker/ca.pem ServerCertPath:C:\Users\thund\.minikube\machines\server.pem ServerKeyPath:C:\Users\thund\.minikube\machines\server-key.pem ClientKeyPath:C:\Users\thund\.minikube\certs\key.pem ServerCertRemotePath:/etc/docker/server.pem ServerKeyRemotePath:/etc/docker/server-key.pem ClientCertPath:C:\Users\thund\.minikube\certs\cert.pem ServerCertSANs:[] StorePath:C:\Users\thund\.minikube}
setting up certificates
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
generating server cert: C:\Users\thund\.minikube\machines\server.pem ca-key=C:\Users\thund\.minikube\certs\ca.pem private-key=C:\Users\thund\.minikube\certs\ca-key.pem org=thund.minikube san=[192.168.1.84 localhost]
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
I0217 17:33:02.624039    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/docker/ca.pem
I0217 17:33:02.672486    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/docker
I0217 17:33:02.688481    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/docker/server.pem
I0217 17:33:02.695488    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/docker
I0217 17:33:02.709484    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/docker/server-key.pem
I0217 17:33:02.717489    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/docker
Setting Docker configuration on the remote daemon...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo mkdir -p /lib/systemd/system && printf %s "[Unit]
Description=Docker Application Container Engine
Documentation=https://docs.docker.com
After=network.target  minikube-automount.service docker.socket
Requires= minikube-automount.service docker.socket

[Service]
Type=notify

# DOCKER_RAMDISK disables pivot_root in Docker, using MS_MOVE instead.
Environment=DOCKER_RAMDISK=yes


# This file is a systemd drop-in unit that inherits from the base dockerd configuration.
# The base configuration already specifies an 'ExecStart=...' command. The first directive
# here is to clear out that command inherited from the base configuration. Without this,
# the command from the base configuration and the command specified here are treated as
# a sequence of commands, which is not the desired behavior, nor is it valid -- systemd
# will catch this invalid input and refuse to start the service with an error like:
#  Service has more than one ExecStart= setting, which is only allowed for Type=oneshot services.
ExecStart=
ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:2376 -H unix:///var/run/docker.sock --tlsverify --tlscacert /etc/docker/ca.pem --tlscert /etc/docker/server.pem --tlskey /etc/docker/server-key.pem --label provider=hyperv --insecure-registry 10.96.0.0/12
ExecReload=/bin/kill -s HUP $MAINPID

# Having non-zero Limit*s causes performance problems due to accounting overhead
# in the kernel. We recommend using cgroups to do container-local accounting.
LimitNOFILE=infinity
LimitNPROC=infinity
LimitCORE=infinity

# Uncomment TasksMax if your systemd version supports it.
# Only systemd 226 and above support this version.
TasksMax=infinity
TimeoutStartSec=0

# set delegate yes so that systemd does not reset the cgroups of docker containers
Delegate=yes

# kill only the docker process, not all processes in the cgroup
KillMode=process

[Install]
WantedBy=multi-user.target
" | sudo tee /lib/systemd/system/docker.service
SSH cmd err, output: <nil>: [Unit]
Description=Docker Application Container Engine
Documentation=https://docs.docker.com
After=network.target  minikube-automount.service docker.socket
Requires= minikube-automount.service docker.socket

[Service]
Type=notify

# DOCKER_RAMDISK disables pivot_root in Docker, using MS_MOVE instead.
Environment=DOCKER_RAMDISK=yes


# This file is a systemd drop-in unit that inherits from the base dockerd configuration.
# The base configuration already specifies an 'ExecStart=...' command. The first directive
# here is to clear out that command inherited from the base configuration. Without this,
# the command from the base configuration and the command specified here are treated as
# a sequence of commands, which is not the desired behavior, nor is it valid -- systemd
# will catch this invalid input and refuse to start the service with an error like:
#  Service has more than one ExecStart= setting, which is only allowed for Type=oneshot services.
ExecStart=
ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:2376 -H unix:///var/run/docker.sock --tlsverify --tlscacert /etc/docker/ca.pem --tlscert /etc/docker/server.pem --tlskey /etc/docker/server-key.pem --label provider=hyperv --insecure-registry 10.96.0.0/12
ExecReload=/bin/kill -s HUP

# Having non-zero Limit*s causes performance problems due to accounting overhead
# in the kernel. We recommend using cgroups to do container-local accounting.
LimitNOFILE=infinity
LimitNPROC=infinity
LimitCORE=infinity

# Uncomment TasksMax if your systemd version supports it.
# Only systemd 226 and above support this version.
TasksMax=infinity
TimeoutStartSec=0

# set delegate yes so that systemd does not reset the cgroups of docker containers
Delegate=yes

# kill only the docker process, not all processes in the cgroup
KillMode=process

[Install]
WantedBy=multi-user.target

[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl -f enable docker
SSH cmd err, output: <nil>: Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/systemd/system/docker.service.

[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl daemon-reload
SSH cmd err, output: <nil>:
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl -f restart docker
SSH cmd err, output: <nil>:
setting minikube options for container-runtime
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo mkdir -p /etc/sysconfig && printf %s "
CRIO_MINIKUBE_OPTIONS='--insecure-registry 10.96.0.0/12 '
" | sudo tee /etc/sysconfig/crio.minikube
SSH cmd err, output: <nil>:
CRIO_MINIKUBE_OPTIONS='--insecure-registry 10.96.0.0/12 '

[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl daemon-reload
SSH cmd err, output: <nil>:
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl -f restart crio
SSH cmd err, output: <nil>:
Getting VM IP address...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Moving files into cluster...
I0217 17:33:27.066736    9648 kubeadm.go:258] Container runtime flag provided with no value, using defaults.
Downloading kubelet v1.13.2
Downloading kubeadm v1.13.2
Finished Downloading kubeadm v1.13.2
I0217 17:33:39.775026    9648 ssh_runner.go:101] SSH: sudo rm -f /usr/bin/kubeadm
I0217 17:33:39.784025    9648 ssh_runner.go:101] SSH: sudo mkdir -p /usr/bin
Finished Downloading kubelet v1.13.2
I0217 17:33:56.441093    9648 ssh_runner.go:101] SSH: sudo rm -f /usr/bin/kubelet
I0217 17:33:56.448093    9648 ssh_runner.go:101] SSH: sudo mkdir -p /usr/bin
I0217 17:33:57.397619    9648 ssh_runner.go:101] SSH: sudo rm -f /lib/systemd/system/kubelet.service
I0217 17:33:57.403619    9648 ssh_runner.go:101] SSH: sudo mkdir -p /lib/systemd/system
I0217 17:33:57.414616    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/systemd/system/kubelet.service.d/10-kubeadm.conf
I0217 17:33:57.419615    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/systemd/system/kubelet.service.d
I0217 17:33:57.431618    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/kubeadm.yaml
I0217 17:33:57.437616    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib
I0217 17:33:57.449618    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/kubernetes/manifests/addon-manager.yaml
I0217 17:33:57.454614    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/kubernetes/manifests/
I0217 17:33:57.467615    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/kubernetes/addons/storageclass.yaml
I0217 17:33:57.472614    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/kubernetes/addons
I0217 17:33:57.483615    9648 ssh_runner.go:101] SSH: sudo rm -f /etc/kubernetes/addons/storage-provisioner.yaml
I0217 17:33:57.488615    9648 ssh_runner.go:101] SSH: sudo mkdir -p /etc/kubernetes/addons
I0217 17:33:57.500619    9648 ssh_runner.go:101] SSH:
sudo systemctl daemon-reload &&
sudo systemctl enable kubelet &&
sudo systemctl start kubelet
I0217 17:33:57.586623    9648 utils.go:224] ! Created symlink /etc/systemd/system/multi-user.target.wants/kubelet.service → /usr/lib/systemd/system/kubelet.service.
Setting up certs...
I0217 17:33:57.670644    9648 certs.go:47] Setting up certificates for IP: 192.168.1.84
I0217 17:33:59.321035    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/ca.crt
I0217 17:33:59.328024    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.342024    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/ca.key
I0217 17:33:59.350021    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.366023    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/apiserver.crt
I0217 17:33:59.373031    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.388023    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/apiserver.key
I0217 17:33:59.396037    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.411024    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/proxy-client-ca.crt
I0217 17:33:59.420025    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.436023    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/proxy-client-ca.key
I0217 17:33:59.444018    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.458019    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/proxy-client.crt
I0217 17:33:59.467019    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.481022    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/certs/proxy-client.key
I0217 17:33:59.488653    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube/certs/
I0217 17:33:59.503020    9648 ssh_runner.go:101] SSH: sudo rm -f /var/lib/minikube/kubeconfig
I0217 17:33:59.511023    9648 ssh_runner.go:101] SSH: sudo mkdir -p /var/lib/minikube
Connecting to cluster...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Setting up kubeconfig...
I0217 17:34:01.479486    9648 config.go:125] Using kubeconfig:  C:\Users\thund/.kube/config
Stopping extra container runtimes...
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl stop crio
SSH cmd err, output: <nil>:
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl stop rkt-api
SSH cmd err, output: <nil>:
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM minikube ).state
[stdout =====>] : Running

[stderr =====>] :
[executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM minikube ).networkadapters[0]).ipaddresses[0]
[stdout =====>] : 192.168.1.84

[stderr =====>] :
Using SSH client type: native
&{{{<nil> 0 [] [] []} docker [0x834720] 0x8346f0  [] 0s} 192.168.1.84 22 <nil> <nil>}
About to run SSH command:
sudo systemctl stop rkt-metadata
SSH cmd err, output: <nil>:
Starting cluster components...
I0217 17:34:08.637445    9648 ssh_runner.go:137] Run with output:
sudo /usr/bin/kubeadm init --config /var/lib/kubeadm.yaml --ignore-preflight-errors=DirAvailable--etc-kubernetes-manifests --ignore-preflight-errors=DirAvailable--data-minikube --ignore-preflight-errors=Port-10250 --ignore-preflight-errors=FileAvailable--etc-kubernetes-manifests-kube-scheduler.yaml --ignore-preflight-errors=FileAvailable--etc-kubernetes-manifests-kube-apiserver.yaml --ignore-preflight-errors=FileAvailable--etc-kubernetes-manifests-kube-controller-manager.yaml --ignore-preflight-errors=FileAvailable--etc-kubernetes-manifests-etcd.yaml --ignore-preflight-errors=Swap --ignore-preflight-errors=CRI

I0217 17:34:08.684441    9648 utils.go:224] > [init] Using Kubernetes version: v1.13.2
I0217 17:34:08.685438    9648 utils.go:224] > [preflight] Running pre-flight checks
I0217 17:34:08.802474    9648 utils.go:224] !   [WARNING Swap]: running with swap on is not supported. Please disable swap
I0217 17:34:08.918032    9648 utils.go:224] > [preflight] Pulling images required for setting up a Kubernetes cluster
I0217 17:34:08.918032    9648 utils.go:224] > [preflight] This might take a minute or two, depending on the speed of your internet connection
I0217 17:34:08.920037    9648 utils.go:224] > [preflight] You can also perform this action in beforehand using 'kubeadm config images pull'
I0217 17:35:45.911553    9648 utils.go:224] > [kubelet-start] Writing kubelet environment file with flags to file "/var/lib/kubelet/kubeadm-flags.env"
I0217 17:35:45.914557    9648 utils.go:224] > [kubelet-start] Writing kubelet configuration to file "/var/lib/kubelet/config.yaml"
I0217 17:35:45.919555    9648 utils.go:224] > [kubelet-start] Activating the kubelet service
I0217 17:35:46.007573    9648 utils.go:224] > [certs] Using certificateDir folder "/var/lib/minikube/certs/"
I0217 17:35:46.304076    9648 utils.go:224] > [certs] Generating "front-proxy-ca" certificate and key
I0217 17:35:46.870100    9648 utils.go:224] > [certs] Generating "front-proxy-client" certificate and key
I0217 17:35:47.147071    9648 utils.go:224] > [certs] Generating "etcd/ca" certificate and key
I0217 17:35:47.755070    9648 utils.go:224] > [certs] Generating "etcd/peer" certificate and key
I0217 17:35:47.756071    9648 utils.go:224] > [certs] etcd/peer serving cert is signed for DNS names [minikube localhost] and IPs [192.168.1.84 127.0.0.1 ::1]
I0217 17:35:47.909073    9648 utils.go:224] > [certs] Generating "etcd/healthcheck-client" certificate and key
I0217 17:35:48.077073    9648 utils.go:224] > [certs] Generating "apiserver-etcd-client" certificate and key
I0217 17:35:48.455238    9648 utils.go:224] > [certs] Generating "etcd/server" certificate and key
I0217 17:35:48.455238    9648 utils.go:224] > [certs] etcd/server serving cert is signed for DNS names [minikube localhost] and IPs [192.168.1.84 127.0.0.1 ::1]
I0217 17:35:48.457234    9648 utils.go:224] > [certs] Using existing ca certificate authority
I0217 17:35:48.625234    9648 utils.go:224] > [certs] Generating "apiserver-kubelet-client" certificate and key
I0217 17:35:48.626237    9648 utils.go:224] > [certs] Using existing apiserver certificate and key on disk
I0217 17:35:48.826260    9648 utils.go:224] > [certs] Generating "sa" key and public key
I0217 17:35:48.826260    9648 utils.go:224] > [kubeconfig] Using kubeconfig folder "/etc/kubernetes"
I0217 17:35:49.119257    9648 utils.go:224] > [kubeconfig] Writing "admin.conf" kubeconfig file
I0217 17:35:49.535322    9648 utils.go:224] > [kubeconfig] Writing "kubelet.conf" kubeconfig file
I0217 17:35:49.637323    9648 utils.go:224] > [kubeconfig] Writing "controller-manager.conf" kubeconfig file
I0217 17:35:49.845337    9648 utils.go:224] > [kubeconfig] Writing "scheduler.conf" kubeconfig file
I0217 17:35:49.847322    9648 utils.go:224] > [control-plane] Using manifest folder "/etc/kubernetes/manifests"
I0217 17:35:49.847322    9648 utils.go:224] > [control-plane] Creating static Pod manifest for "kube-apiserver"
I0217 17:35:49.853739    9648 utils.go:224] > [control-plane] Creating static Pod manifest for "kube-controller-manager"
I0217 17:35:49.854330    9648 utils.go:224] > [control-plane] Creating static Pod manifest for "kube-scheduler"
I0217 17:35:49.855326    9648 utils.go:224] > [etcd] Creating static Pod manifest for local etcd in "/etc/kubernetes/manifests"
I0217 17:35:49.859336    9648 utils.go:224] > [wait-control-plane] Waiting for the kubelet to boot up the control plane as static Pods from directory "/etc/kubernetes/manifests". This can take up to 4m0s
I0217 17:36:29.862395    9648 utils.go:224] > [kubelet-check] Initial timeout of 40s passed.
I0217 17:37:04.365934    9648 utils.go:224] > [apiclient] All control plane components are healthy after 74.505993 seconds
I0217 17:37:04.369920    9648 utils.go:224] > [uploadconfig] storing the configuration used in ConfigMap "kubeadm-config" in the "kube-system" Namespace
I0217 17:37:04.671378    9648 utils.go:224] > [kubelet] Creating a ConfigMap "kubelet-config-1.13" in namespace kube-system with the configuration for the kubelets in the cluster
I0217 17:37:05.200422    9648 utils.go:224] > [patchnode] Uploading the CRI Socket information "/var/run/dockershim.sock" to the Node API object "minikube" as an annotation
I0217 17:37:05.715980    9648 utils.go:224] > [mark-control-plane] Marking the node minikube as control-plane by adding the label "node-role.kubernetes.io/master=''"
I0217 17:37:06.282062    9648 utils.go:224] > [bootstrap-token] Using token: x5b58x.7m94nvc62p9k6qxg
I0217 17:37:06.283063    9648 utils.go:224] > [bootstrap-token] Configuring bootstrap tokens, cluster-info ConfigMap, RBAC Roles
I0217 17:37:06.312061    9648 utils.go:224] > [bootstraptoken] configured RBAC rules to allow Node Bootstrap tokens to post CSRs in order for nodes to get long term certificate credentials
I0217 17:37:06.346069    9648 utils.go:224] > [bootstraptoken] configured RBAC rules to allow the csrapprover controller automatically approve CSRs from a Node Bootstrap Token
I0217 17:37:06.566010    9648 utils.go:224] > [bootstraptoken] configured RBAC rules to allow certificate rotation for all node client certificates in the cluster
I0217 17:37:06.573007    9648 utils.go:224] > [bootstraptoken] creating the "cluster-info" ConfigMap in the "kube-public" namespace
I0217 17:37:08.171608    9648 utils.go:224] > [addons] Applied essential addon: CoreDNS
I0217 17:37:09.108170    9648 utils.go:224] > [addons] Applied essential addon: kube-proxy
I0217 17:37:09.112169    9648 utils.go:224] > Your Kubernetes master has initialized successfully!
I0217 17:37:09.117187    9648 utils.go:224] > To start using your cluster, you need to run the following as a regular user:
I0217 17:37:09.119191    9648 utils.go:224] >   mkdir -p $HOME/.kube
I0217 17:37:09.125170    9648 utils.go:224] >   sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
I0217 17:37:09.126187    9648 utils.go:224] >   sudo chown $(id -u):$(id -g) $HOME/.kube/config
I0217 17:37:09.130188    9648 utils.go:224] > You should now deploy a pod network to the cluster.
I0217 17:37:09.134198    9648 utils.go:224] > Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
I0217 17:37:09.140186    9648 utils.go:224] >   https://kubernetes.io/docs/concepts/cluster-administration/addons/
I0217 17:37:09.143166    9648 utils.go:224] > You can now join any number of machines by running the following on each node
I0217 17:37:09.144163    9648 utils.go:224] > as root:
I0217 17:37:09.144163    9648 utils.go:224] >   kubeadm join localhost:8443 --token x5b58x.7m94nvc62p9k6qxg --discovery-token-ca-cert-hash sha256:efcc02cd058437adb9144094bf30490523c239da623d424c273d95e799213fdf
I0217 17:37:09.147173    9648 loader.go:359] Config loaded from file C:\Users\thund/.kube/config
I0217 17:37:09.160170    9648 round_trippers.go:383] GET https://192.168.1.84:8443/apis/rbac.authorization.k8s.io/v1beta1/clusterrolebindings/minikube-rbac?timeout=1m0s
I0217 17:37:09.161172    9648 round_trippers.go:390] Request Headers:
I0217 17:37:09.161172    9648 round_trippers.go:393]     Accept: application/json, */*
I0217 17:37:09.167169    9648 round_trippers.go:393]     User-Agent: minikube.exe/v0.0.0 (windows/amd64) kubernetes/$Format
I0217 17:37:09.461831    9648 round_trippers.go:408] Response Status: 404 Not Found in 294 milliseconds
I0217 17:37:09.464846    9648 round_trippers.go:383] POST https://192.168.1.84:8443/apis/rbac.authorization.k8s.io/v1beta1/clusterrolebindings?timeout=1m0s
I0217 17:37:09.466835    9648 round_trippers.go:390] Request Headers:
I0217 17:37:09.470840    9648 round_trippers.go:393]     User-Agent: minikube.exe/v0.0.0 (windows/amd64) kubernetes/$Format
I0217 17:37:09.472834    9648 round_trippers.go:393]     Accept: application/json, */*
I0217 17:37:09.472834    9648 round_trippers.go:393]     Content-Type: application/json
I0217 17:37:09.540829    9648 round_trippers.go:408] Response Status: 201 Created in 67 milliseconds
Verifying kubelet health ...I0217 17:37:09.542821    9648 ssh_runner.go:137] Run with output: sudo systemctl is-active kubelet
I0217 17:37:09.553827    9648 utils.go:224] > active

Verifying apiserver health ...I0217 17:37:09.599825    9648 kubeadm.go:99] https://192.168.1.84:8443/healthz response: <nil> &{Status:200 OK StatusCode:200 Proto:HTTP/1.1 ProtoMajor:1 ProtoMinor:1 Header:map[Date:[Sun, 17 Feb 2019 17:37:09 GMT] Content-Length:[2] Content-Type:[text/plain; charset=utf-8]] Body:0xc000044880 ContentLength:2 TransferEncoding:[] Close:false Uncompressed:false Trailer:map[] Request:0xc000418000 TLS:0xc0005e8000}

Kubectl is now configured to use the cluster.
Loading cached images from config file.


Everything looks great. Please enjoy minikube!
PS C:\> .\kubectl get nodes
error: group map[apps:0xc082382e70 authentication.k8s.io:0xc082382ee0 autoscaling:0xc0823830a0 certificates.k8s.io:0xc0823832d0 federation:0xc082382930 policy:0xc082382000 admissionregistration.k8s.io:0xc08220f570 :0xc082382e00 batch:0xc082383260 storage.k8s.io:0xc0823820e0 events.k8s.io:0xc08220f500 coordination.k8s.io:0xc08220f5e0 authorization.k8s.io:0xc082383030 componentconfig:0xc082383340 extensions:0xc082383420 rbac.authorization.k8s.io:0xc082382070 apiextensions.k8s.io:0xc08220f650] is already registered
PS C:\> kubectl get nodes
NAME       STATUS    ROLES     AGE       VERSION
minikube   Ready     master    1m        v1.13.2
PS C:\> kubectl get nodes
NAME       STATUS    ROLES     AGE       VERSION
minikube   Ready     master    3d        v1.13.2
PS C:\>
```

