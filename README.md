# Docker notes
Udemy docker course
https://www.udemy.com/learn-docker/learn/v4/content

# Why use docker

![alt text](https://github.com/duozhanggithub/udemy-docker-course/blob/master/explaination%20of%20containers.png)

# Docker basic operations

docker run

docker run Ubuntu:17.04 (tag), run a certain version ubuntu

-run container from an image, for the first time, it also pull an image (from docker hub)

-docker run -d xxx (detach mode)

-docker attach xxx (attach again)

docker ps

-list all running containers

docker ps -a

-all the container, no matter running or not

docker stop 'container id/name'

-stop running a container

docker rm 'container id/name'

-remove container for ever

docker images

-images on docker hub

docker rmi 'name'

-remove images
-The rmi command is used to remove images and the rm command is used to remove containers. 
-To remove an image, you must ensure that no containers are running off of it. 
-You must stop and delete all dependent containers to be able to delete the underlying base image.

docker pull 'image'

-only pull the image, so don not need to download when use it

docker run -it 'image' bash

-run image and use it immediately, if image is ubuntu, then run a base image of ubuntu system
-after enter ubuntu, we can run for example, cat /etc/*release*

# Port mapping

![alt text](https://github.com/duozhanggithub/udemy-docker-course/blob/master/docker%20port%20mapping.png)

docker run -p 8080:8080 jenkins (order is to:from)

docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts

# Docker file

In the format of INSTRUCTION ARGUMENT

FROM

RUN

ADD (add files)

ENV (set environment variables)

WORKDIR (define working directory)

CMD (define default command)

CMD command param1 or CMD ["command" "param1"]

e.g. 

FROM ubuntu

CMD sleep 5 or CMD ["sleep", "5"]

![alt text](https://github.com/duozhanggithub/Docker-notes/blob/master/Dockerfile%20procedures.png)

CMD and ENTRYPOINT

![alt text](https://github.com/duozhanggithub/Docker-notes/blob/master/CMD%20and%20Entrypoint.png)

# Docker compose

![alt text](https://github.com/duozhanggithub/Docker-notes/blob/master/Docker%20compose%20example.png)

# Docker swarm

![alt text](https://github.com/duozhanggithub/Docker-notes/blob/master/Docker%20Swarm.png)

Deploy 5 instances

![alt text](https://github.com/duozhanggithub/Docker-notes/blob/master/Docker%20Swarm%20example.png)

# Docker networking

![alt text](https://github.com/duozhanggithub/Docker-notes/blob/master/Docker%20networking.png)

Docker network: Bridge, None, Host

Bridge: The Bridge network is a private internal network created by Docker on the host. All the containers attached 
to this network by default and they get an internal IP address.

To access any of these containers from the outside world, you must map ports of these containers to the docker host

Host: Another way to access the containers externally is to associate the containers to the host network. This takes out any network isolation between the docker host and the docker container. Meaning if you were to run a web server on port 5000 in a web-app containe.

None: With the none network, containers are not a task to any network and doesn't have any access to the external network or other containers.
