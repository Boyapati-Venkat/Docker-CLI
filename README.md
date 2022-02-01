## Docker CLI Commands
* [Docker Installation](#docker-installation)
* [Docker File Instructions](#docker-file-instructions)
* [Docker CLI Commands](#docker-cli-commands)

## Docker Installation
* File1
```

tool for deploying multi container docker applications

it contains information about containers

Docker Compose is a tool for running multi-container applications on Docker defined using the Compose file format. A Compose file is used to define how the one or more containers that make up your application are configured. Once you have a Compose file, you can create and start your application with a single command: docker-compose up.
docker-compose installation

-------------------------------

sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
           or
sudo apt-get install docker-compose

docker-compose --version


docker-compose.yaml
----------------------------

version: docker compose file format version 3 or 3.1

services: 

volumes:

networks:


sidercor container in kubernetes
docker-compose config
docker-compose up -d(detach)
```
	
## Docker File Instructions
```
  * Docker file Instructions
    --------------------------------
    these are called docker instructions or docker file keywords
    dockerfile instructions can be processed from top to bottom
    
    
    FROM - Indicates the base image for our docker file
    
    eg: tomcat, open-jdk, httpd
    
    MAINTAINER - It will be used to desribe maintainer/author
    
    eg: venkat@tr.com, kiran.b@bitsol.com
    
    COPY - It will be used to copy files from host server to the image 
    
    eg: COPY <srcfile> <dest>
    
    ADD - add also can copy files to the image from hostserver and it will download files from the remote     server. 
    
    it will also copy tar file and will extract it.
    
    eg. add <url> destination add <src> <dest>
    
    RUN - instructions/commands will be executed while creating an image. we can have more than one RUN     keywords in docker file
    
    RUN instruction allows you to install your application and packages requited for it. 
    It executes any commands on top of the current image and creates a new layer by committing the     results. 
    Often you will find multiple RUN instructions in a Dockerfile.
    
    eg. RUN mkdir -p "$CATALINA_HOME"
    
    CMD - it will execute commands while creating the container.
    
    we will use it to start our application while creating the container
    
    eg. sh catalina.sh run  or CMD ["java", "-jar", "springapplication.jar"]
    
    
    ENTRYPOINT - entrypoint also used to execute commands
    
    
    WORKDIR -  we can set working directory for an image/container. all subsequent instructions will be     processed under working directory.
    
    
    EXPOSE - which port is opened or being used in the image. <port>
    
    ENV - env is used to set environment variables. these environment variables will be availble for     image or container. 
    
    eg. ENV JAVA_HOME /usr/bin/java  ENV CATALINA_HOME /usr/local/tomcat
    
    
    USER - user is used to set user for the container or image. if not specified root as default user
    
    eg. USER <username>
    
    LABEL - we can add labels to the image
    
    eg. LABEL <key> <Value>
    refer arg name here
        LABEL branch $branchname
        LABEL environmetname $environment
    
    
    ARG - branchname=dev
    
    ARG - environment=prod
    
    ARG - using arg we can define variables
    
    while creating an image we can pass arguments as below
    
    docker build -t <imagename> --buil-arg branchname=dev
    
    VOLUME - volume keyword is used to mount a container folder with host folder.
```
	
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
  
