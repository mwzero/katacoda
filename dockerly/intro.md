# What is Docker?

Docker is the toolkit developed by [Docker.com](www.docker.com) to create, distribute and run cointainers;

Containers allow to deploy and run applications in an isolated environment separated from the infrastructure; in this way the execution environment will be the same whether the application is deployed in the customer data center, in the cloud or anywhere.

The container is like a lightweight virtual machine because it was created to hold only the application dependencies, without installing the entire operating system. 

>Containers running on a host use the same machine kernel.

The main advantages are:

- Software Distribution:
    - faster and safer: the software is distributed via containers that already contain all dependencies and cannot be changed
    - run anywhere: containers can be run anywhere
- Isolation: each container is isolated from the other; This allows to run many containers in parallel on a given system.

The main components of Docker are:

- Docker Engine 
- Images and containers

## Docker Engine

Docker Engine is a client-server based application responsible for creating and running containers.

! [] (docker-engine.jpg)

Docker Engine is composed of a daemon process to control and manage containers and two different layers to access its functionality:
    * A REST API as an interface to the daemon
    * A command line client to send Docker commands to the server

Docker CLI is the tool used in this short course to interact with Docker.

## Images and containers
A Docker image is a read-only model that contains a set of instructions for creating a container that can run on the Docker platform.

Docker CLI allows you to create, run, stop or delete a container.

Mostly, an image is based on another image, with some additional customization in the image but it is possible to build our own image.

### Dockerfile
The Dockerfile contains the commands to create the image. Each statement in a Dockerfile creates a new layer in the image.
If we modify the Dockerfile, only the layers that have been modified are rebuilt.

### Docker Registry
Images are distributed using a private or public registry called
"Docker Registry".
The images are "pushed" to be stored in the registry and "extracted" to be available to the customer.