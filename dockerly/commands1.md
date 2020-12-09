# Image and Container

First: running a container starting from a well-know image

`docker run --name mynginx -p 80:80 -d nginx`{{execute}}

the run command use the following parameter: 

- --name specify the name of container
- -p binding internal port with host port
- -d execute the conainter in background 

tha last parameter is the name of Docker Image.