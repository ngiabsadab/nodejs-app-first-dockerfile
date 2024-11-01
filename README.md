# Docker CLI

Build an Image from a Dockerfile

    docker build -t <image_name>
    docker build .



# Container

Create and run a container from an image, with a custom name

    docker run --name <container_name> <image_name>
    docker run node

Run a container with and publish a container’s port(s) to the host

    docker run -p <host_port>:<container_port> <image_name>
    docker run -p 3000:80 afed756c4069


Run a container in the background

    docker run -d <image_name> 
    docker run -p 3000:80 -d afed756c4069
    // after run, it will generate ID of the new container


Start or stop an existing container

    docker start|stop <container_name> (or <container-id>)
    docker start jolly_hertz
    docker stop jolly_hertz

Remove a stopped container

    docker rm <container_name>
    docker rm jolly_hertz

Open a shell inside a running container

    docker exec -it <container_name> sh

Fetch and follow the logs of a container

    docker logs -f <container_name>
    docker logs -f jolly_hertz
    // when you want to see logs after run background.

To inspect a running container

    docker inspect <container_name> (or <container_id>)

To list currently running containers:

    docker ps

List all docker containers (running and stopped):

    docker ps --all

View resource usage stats

    docker container stats

Inspect

    docker inspect afed756c4069

Copy 

    docker cp dummy/. elated_black:/test
    docker cp elated_black:/test dummy
    docker cp elated_black:/test/test.txt dummy


Assign a name to the container

    docker run -p 3000:80 -d --rm --name fistapp afed756c4069
    
![assign_name_to_the_container.png](assets/images/assign_name_to_the_container.png)



Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE - name or repository is "goals" - tag is "latest"


    docker build -t goals:latest .
    docker build -t goals:22 .


    old docker run -p 3000:80 -d --rm --name fistapp afed756c4069
    new docker run -p 3000:80 -d --rm --name fistapp goals:latest

    
    
![tag_refers_to_image.png](assets/images/tag_refers_to_image.png)


If you want to remove all images, incl. tagged images, you need to run

    docker run docker image prune -a
    
