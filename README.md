# udemy-docker-course
Selected exercises solutions for udemy docker course
https://www.udemy.com/learn-docker/learn/v4/content

docker run

-run container from an image, for the first time, it also pull an image

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


