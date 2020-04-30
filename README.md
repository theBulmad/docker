# docker
Docker Notes

`Image` - the application we want to run

`Container` - an instance of that image running as a process

Docker commands

Tip: USE  `docker --help` instead of this

`docker version` - verify that docker engine is running and additional cli and server info

`docker info` - additional info on docker engine, number of containers running etc

`docker ps` - lists processes running inside of docker engine

`docker container ls` - lists running containers

`docker image ls` - lists images

`docker container run --publish 8888:80 [imageName]` - publishes the image to a container and runs it on localhost:8888 port (if image does not exist locally, pulls from hub.docker.com registry)

`docker start -ai [containerName]` - starts container

`docker stop [containerID/imageName]` - stops container that is running on specified name or containerID (on linux if process is running on commandline ctrl+c works)

`docker run --publish(or -p) 8888:80 --detach(or -d) --name [Name] [imageName]` - runs container in the background, --name allows you to add a unique name for the container

`docker container logs [containerName]` - logs for specified container name

`docker container top [containerName]` - display the running processes of a container

`docker container rm [first 3 values from containerID i.e. 81c] [add another 3 for next containerID]` - removes multiple non-running   containers at once

`docker container run --publish 8888:80 --name webhost -d nginx:1.11 nginx -T` - example of command that specifies host listening port, verion of image and run on start

`docker container run -it --name [name] [image] [command e.g. bash]` - allows you to enter into the container using an interactive shell
