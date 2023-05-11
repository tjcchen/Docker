## Docker
On Linux, Docker uses the resource isolation features of the Linux kernel, such as `cgroups` and `kernel namespaces` and a `union-capable file system`, such as `OverlayFS`, to allow containers to run within a single Linux instance, avoiding the overhead of starting and maintaining virtual machines.

## Concepts
CGroups: cgroups (abbreviated from control groups) is a Linux kernel feature that limits, accounts for, and isolates the resource usage (CPU, memory, disk I/O, network, etc.) of a collection of processes.

Namespaces: Namespaces are a feature of the Linux kernel that partitions kernel resources such that one set of processes sees one set of resources while another set of processes sees a different set of resources.

Union FS: Union FS is a filesystem service for Linux, FreeBSD and NetBSD.

## Advantages of Docker Technology
1. Uses system resources more efficiently, compared to virtual machine. Since docker utilize system `cgroup`, `kernel`, `Union FS` features, and share systems resources with main host directly.

2. Faster bootstrap time, no need to launch your VM.

3. Consistent running environment - same docker mirror image

4. Contiuously CI / CD

5. Migrate your code with ease

6. Easy maintaince and extentions

## Most-used Commands
```bash
# check current system info
uname -a

# docker run
docker run
  -it interactive
  -d  deamon background
  -p  port mapping
  -v  disk mounting

# Eg: centos
docker run -it centos bash

# start a container
docker start

# stop a container
docker stop

# check container process
docker ps

# Eg: check running centos container
docker ps | grep centos

# check docker mainfest
docker inspect <containerID> -> eg: docker inspect e56ebc669fbd

# copy a file to the container
docker cp file1 <containerid>:/file-to-path

# docker pull
docker pull centos

# list all docker images
docker images
```

## Get to Know Docker
```bash
# Basic Dockerfile structure
FROM ubuntu
ENV MY_SERVICE_PORT=80
ADD bin/amd64/httpserver /httpserver
ENTRYPOINT /httpserver

# Transform Dockerfile to a mirror image
docker build -t tjcchen/httpserver:${tag} . # build
docker push tjcchen/httpserver:v1.0         # push mirror image to remote

# Run the docker container( in remote container )
docker run -d tjcchen/httpserver:v1.0
```

## Links
- Documentation: https://docs.docker.com/

- Overview: https://docs.docker.com/get-started/overview/

- Container Standard: https://opencontainers.org/

- Two Major Standards of Open Container Initiative(OCI): Runtime Specification, Image Specification

## License
MIT
