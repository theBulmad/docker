# docker

# Docker Notes

`Image` - the application we want to run

`Container` - an instance of that image running as a process

# Docker tab-completion for windows powershell

`Install-Module DockerCompletion -Scope CurrentUser`

`Import-Module DockerCompletion`

# Docker commands

Tip: USE  `docker --help` instead of this

`docker version` - verify that docker engine is running and additional cli and server info

`docker info` - additional info on docker engine, number of containers running etc

`docker ps` - lists processes running inside of docker engine

`docker container ls` - lists running containers

`docker pull [imageName]` - no need to explain

`docker image ls` - lists images

`docker container run --publish 8888:80 [imageName]` - publishes the image to a container and runs it on localhost:8888 port (if image does not exist locally, pulls from hub.docker.com registry)

`docker start [containerName]` - starts container

`docker start -ai [containerName]` - starts container with interactive shell

`docker container exec -it [containerName] [command e.g. bash]` - runs an additional process on top of the existing container, exit kills the additional process

`docker stop [containerID/imageName]` - stops container that is running on specified name or containerID (on linux if process is running on commandline ctrl+c works)

`docker run --publish(or -p) 8888:80 --detach(or -d) --name [Name] [imageName]` - runs container in the background, --name allows you to add a unique name for the container

`docker container logs [containerName]` - logs for specified container name

`docker container top [containerName]` - display the running processes of a container

`docker container rm [first 3 values from containerID i.e. 81c] [add another 3 for next containerID]` - removes multiple non-running   containers at once

`docker container run --publish 8888:80 --name webhost -d nginx:1.11 nginx -T` - example of command that specifies host listening port, verion of image and run on start

`docker container run -it --name [name] [image] [command e.g. bash]` - allows you to enter into the container using an interactive shell

# Docker Network

`docker network ls` - show networks

`docker network inspect [networkName]` - inspect a network

`docker network create --driver` - create a network

`docker network connect` - attach a network to a container

`docker network disconnect` - detach a network from a container

`docker container port [containerName]` - prints incoming traffic from outside port into inside port

`docker container inspect --format '{{ .NetworkSettings.IPAddress }}' [containerName]` - check docker ip (grep also works)

