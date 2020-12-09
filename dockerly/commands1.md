# Basic Docker Commands

- docker pull [image]: Pulls the image from the remote
registry to your local filesystem
- docker run [image]: Creates a container from the specific image
- docker ps: Lists the active containers
- docker exec [container]: Executes a command inside the container
- docker images: Lists the images on your machine
- docker ps -a: Lists all the containers regardless of their states
- docker rm [container]: Removes a running container
- docker rmi [image]: Removes an image from your machine
- docker build: Creates an image by following the instructions provided in a special file called a Dockerfile

## Docker pull

## Docker run

First: running a container starting from a well-know image

`docker run --name mynginx -p 80:80 -d nginx`{{execute}}

the run command use the following parameter: 

- --name specify the name of container
- -p binding internal port with host port
- -d execute the conainter in background 

tha last parameter is the name of Docker Image.

We can comment the output

Unable to find image 'nginx:latest' locally <i></i>
latest: Pulling from library/nginx          <i></i>
852e50cd189d: Pull complete                 <i></i>
571d7e852307: Pull complete                 <i></i>
addb10abd9cb: Pull complete                 <i></i>
d20aa7ccdb77: Pull complete                 <i></i>
8b03f1e11359: Pull complete                 <i></i>
Digest: sha256:6b1daa9462046581ac15be20277a7c75476283f969cb3a61c8725ec38d3b01c3
Status: Downloaded newer image for nginx:latest
d5615edc791895040eabdd1f826a7a37dcf57ca7a3112a4b26894427e51dbc58

The last row reports the docker container id. 

## Docker ps

## Docker exec