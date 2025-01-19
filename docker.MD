#   If not able to make image due to any command in docker file Run below
`
docker run -it myweb /bin/bash
`
#   To check process inside the container
`
ps -ef
`

#   To exit from this shell (All the process will be killed)
`
Type exit
`


# To build the docker Image from the Dockerfile we just created, simply run the following command. I name it my-app, but feel free to change it to what ever you want. Also don’t forget the . at last.

`docker build -t my-app .
`

# Once the image is created, we can run it by

`docker run -p 3000:3000 my-app

-p ⇒ let’s you create a port mapping
-d. ⇒ Let’s you run it in detatched mode
`

# To list all docker images

`sudo docker images
`

# To list all docker container
`docker ps -a
`

# Passing in env variables
`sudo docker run -p 3000:3000 -e DATABASE_URL="postgres://avnadmin:AVNS_EeDiMIdW-dNT4Ox9l1n@pg-35339ab4-harkirat-d1b9.a.aivencloud.com:25579/defaultdb?sslmode=require" image_name
`

#   Run command without using SUDO
`
sudo usermod -aG docker your_username
`
In place of "your_username" write your system username which you can get using `whoami` in terminal.
Now Restart docker again
`
sudo systemctl restart docker
`

### Important Docker Commands:

(1) List All Docker Images In host Machine (Your System)

docker images

(2) List All Container

docker ps

(3) List All Running Container

docker ps -a

(4) Execute command on container

docker exec -it <container-id> /bin/bash

(5) This command starts one or more stopped containers

docker start my-container

(6) This command stops one or more running containers

docker stop my-container

(7) This command restarts one or more running containers.It stops and then starts the specified containers.

docker restart my-container

(8) This command removes one or more stopped containers. It does not remove running containers by default, but you can use the -f option to force removal of running containers.

docker rm my-container

(9) This command is used to remove one or more Docker images from your local system.

docker rmi my-image-name
OR Force Remove when any error comes
docker rmi -f my-image-name

(10) The Simplest  docker build command is used to build a Docker image from a Dockerfile.

docker build -t my-image .

(11) docker rmi my-image

docker run -p 3000:3000 my-app

OR

docker run -d -p 8080:80 --name my-container my-image:latest


Explanation:

Here are some common options you might use with docker run:

    -d or --detach: Run the container in detached mode (in the background).

    -p or --publish: Publish a container's port(s) to the host.

    -v or --volume: Bind mount a volume from the host to the container.

    -e or --env: Set environment variables inside the container.

    --name: Assign a name to the container.

    --rm: Automatically remove the container when it exits.

    --network: Connect the container to a network.

(12) To inspect a Docker container - with container's name or ID
    docker inspect myweb

(13) See docker container logs Entrypoint and CMD command Output
 docker logs <image-name>

# Docker compose commands

(1) Build and Run docker image
    docker compose up --build

(2) Remove all docker images Running
    docker compose down



# Multistage Dockerfile Example
https://github.com/processing/p5.js-web-editor


#   If Docker commands not running without SUDO
`
export DOCKER_HOST=unix:///var/run/docker.sock
echo $DOCKER_HOST
docker ps
`