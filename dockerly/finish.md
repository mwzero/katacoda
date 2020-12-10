# Docker and Linux feature

Docker Engine uses the features of the Linux kernel to manage the containers and the resources they can use (cpu, network, ram etc ..).

Docker Engine uses: 
- Linux Kernel namespaces
- cgroups
- UnionFs

Docker Engine adds the namespaces, control groups & UnionFS into a file using the format [libcontainer](https://github.com/opencontainers/runc/tree/master/libcontainer).

In the future the format could be changed. Docker take part of group to define an open container: [The Open Container Project](https://www.docker.com/blog/open-container-project-foundation/).

Partecipants: 
![The Open Container Project](otp.png)

# Linux namespaces

The Linux Kernel namespaces feature allows to create isolated environments ( or better sandboxing processes from one another).

Docker creates a set of Linux namespaces when a new container is running:

- pid : Process isolation (PID: Process ID).
- net : Managing network interfaces (NET: Networking)
- ipc : Managing access to IPC (InterProcess Communication) resources
- mnt : Managing filesystem mount points (MNT: Mount).
- uts : Isolating kernel and version identifiers. (UTS: Unix Timesharing System).

# Control Groups

Control Groups (cgroups) are a feature of the Linux kernel to limit the access processes and containers have to system resources such as CPU, RAM, IOPS and network. 

# Union File Systems

"Unionfs is a filesystem service for Linux, FreeBSD and NetBSD which implements a union mount for other file systems. It allows files and directories of separate file systems, known as branches, to be transparently overlaid, forming a single coherent file system. Contents of directories which have the same path within the merged branches will be seen together in a single merged directory, within the new, virtual filesystem." (Wikipedia)

Docker Engine using union file system provide the building blocks to containers.

Docker Engine uses many UnionFS variants some of including are AUFS, btrfs, vfs, Device Mapper, etc.
