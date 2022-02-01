## Docker CLI Commands
*  [Docker Installation](# Docker Installation)
* [Docker File Instructions](#Docker File Instructions)
* [Docker CLI Commands](#Docker CLI Commands)
## Table of contents
* [General  info]
* [Technologies](#technologies)
* [Setup](#setup)

## Docker Installation
This project is simple Lorem ipsum dolor generator.
	
## Docker File Instructions
Project is created with:
* Lorem version: 12.3
* Ipsum version: 2.33
* Ament library version: 999
	
## Docker CLI Commands
To run this project, install it locally using npm:

```shell script
  *. Build
    docker build -t <hub-user>/<repo-name>:<imagetag> <pathof docker file>
    docker build -t 'venkatondevops/nginxserver:1' .
    docker push 
    docker login -u <uname> -p <password> <url>
    docker images
    docker image ls
    docker image inspect imagename
    docker inspect imageid/imagename
    docker history imageid/imagename ----  to see only layers
    docker inspect containerid/containername
    docker rmi -f(force) imageid/imagename
    docker rmi -f(force) imageid/imagename imageid/imagename imageid/imagename - to delete all
    docker rmi -f $(docker images -q)
    docker images -q --  list all image ids
    docker tag image -- to tag image to the repository
    docker ps
    docker container ls
    docker container ls -a
    docker ps -a all containers
    docker ps -aq
    docker container ls -aq
    docker start containerid/name
    docker restart containerid/name
    docker stop containerid/name
    docker kill containerid/name
    docker pause containerid/name
    docker unpause containerid/name
    docker system prune -a  -- it will remove both unused and dangling images
    docker images -f dangling=true -- list dangling images
    docker rmi $(docker images -f dangling=true -q)
    docker images --quiet --filter=dangling=true | xargs --no-run-if-empty docker rmi
    docker image prune 
    docker rm -f container-name/container-id
    docker system prune ---- delte all stoped container, networks, dangling,
    docker run -d --name contname -p <hostport>:<contport> imageid
    dockertrustedregistry(Docker enterprise edition)
    docker rm $(docker ps -aq --filter status="exited")
    docker rm -f $(docker ps -aq )

```
  
