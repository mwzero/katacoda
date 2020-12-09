# What is Docker?

Docker allows you to deploy and run your application in an isolated environment separate from the infrastructure; in this way the execution environment will be the same whether your application is deployed to the customer, in the cloud or wherever you want.

The isolated environment is called a "container" and is like a lightweight virtual machine because the container can be created using only application dependencies without installing the entire operating system.

Containers running on a host use the same machine kernel.

Docker is the toolkit developed by www.docker.com to create, distribute and run the cointainer;

Docker containers are distributed using a binary format called "Images".

Containers in the target environment are run from images.

>Which advantages?

- Deployment: 
    - faster and safe;  the software is distribuited via containers which already contain all the dependencies and is not possible to modify it
    - execution everywhere: the Docker containers are executable everywhere such as developer laptop, data center on-premise and obviously in cloud
- Isolation: each container is isolated from the other; This allows to execute many containers in parallel on a given system. 

# Core Components 

Docker is composed by: 
- Docker Engine
- Docker Daemon
- Images and Containers
- Docker Client
- Docker Registries

## Docker Engine
The Docker engine is a part of Docker which create and run the Docker containers. The docker container is a live running instance of a docker image. Docker Engine is a client-server based application with following components 

* A server which is a continuously running service called a daemon process.
* A REST API which interfaces the programs to use talk with the daemon and give instruct it what to do.
* A command line interface client.

[](docker-engine.jpg)

The command line interface client uses the Docker REST API to interact with the Docker daemon through using CLI commands. Many other Docker applications also use the API and CLI. The daemon process creates and manage Docker images, containers, networks, and volumes.

## The Docker Daemon

The docker daemon process is used to control and manage the containers. The Docker daemon listens to only Docker API requests and manages Docker images, containers, networks, and volumes. It also communicates with other daemons to manage Docker services.

## The Docker Client
Docker client is the primary service using which Docker users communicate with the Docker. When we use commands “docker run” the client sends these commands to dockerd, which execute them out.

The command used by docker depend on Docker API. In Docker client can interact more than one daemon process.

## Docker Images
The Docker images are building the block of docker or docker image is a read-only template with instructions to create a Docker container. Docker images are the most build part of docker life cycle.

Mostly, an image is based on another image, with some additional customization in the image.

We can build an image which is based on the centos image, which can install the Nginx web server with required application and configuration details which need to make the application run.

We can create our own images or only use those created by others and published in registry directory. To build our own image is very simple because we need to create a Dockerfile with some syntax contains the steps that needed to create the image and make to run it.

Each instruction in a Dockerfile creates a new layer in the image. If we need to modify the Dockerfile we can do the same and rebuild the image, the layers which have changed are rebuilt.

This is why images are so lightweight, small, and fast when compared to other virtualization technologies.

## Docker Registries
A Docker registry keeps Docker images. We can run our private registry.

When we run the docker pull and docker run commands, the required images are pulled from our configured registry directory.

Using Docker push command, the image can be uploaded to our configured registry directory.

## Docker Containers
A container is the instance of an image. We can create, run, stop, or delete a container using the Docker CLI. We can connect a container to more than one networks, or even create a new image based on its current state.

By default, a container is well isolated from other containers and its system machine. A container defined by its image or configuration options that we provide during to create or run it.

Namespaces
Docker using a service named namespaces is provided to the isolated environment called container. When we run a container, Docker creates a set of namespaces for that particular container. The namespaces provide a layer of isolation. Some of the namespace layer is -

Namespace PID provides isolation for the allocation of the process, lists of processes with details.In new namespace is isolated from other processes in its “parent” namespace still see all processes in child namespace
Namespace network isolates the network interface controllers, IP tables firewall rules, routing tables etc. Network namespaces can be connected with each other using the virtual Ethernet device.
Control Groups
Docker Engine in Linux relies on named control groups. A group limits the application to a predefined set of resources.

Control groups used by Docker Engine to share the available hardware resources to containers.

Using control groups, we can define the memory available to a specific container.

## Union File Systems
Union file systems, a file system which is used by creating layers, making them lightweight in size and faster. Docker Engine using union file system provide the building blocks to containers.

Docker Engine uses many UnionFS variants some of including are AUFS, btrfs, vfs, Device Mapper, etc.

Container Format
Docker Engine adds the namespaces, control groups & UnionFS into a file called a container format. The default format for the container is lib container.