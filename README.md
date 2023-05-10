## Docker
On Linux, Docker uses the resource isolation features of the Linux kernel, such as `cgroups` and `kernel namespaces` and a `union-capable file system`, such as `OverlayFS`, to allow containers to run within a single Linux instance, avoiding the overhead of starting and maintaining virtual machines.

## Concepts
CGroups: cgroups (abbreviated from control groups) is a Linux kernel feature that limits, accounts for, and isolates the resource usage (CPU, memory, disk I/O, network, etc.) of a collection of processes.

Namespaces: Namespaces are a feature of the Linux kernel that partitions kernel resources such that one set of processes sees one set of resources while another set of processes sees a different set of resources.

Union FS: Union FS is a filesystem service for Linux, FreeBSD and NetBSD

## License
MIT
