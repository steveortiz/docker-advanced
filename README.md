# Docker plus

Course outline
- Single Stage vs Multi-stage
- How to build, tag, and push an image
- Docker compose, a closer look
- Volumes, what where and why
- Troubleshooting, debugging

## Cheat sheet

There are many commands available and a full list can always been seen by running `docker --help` but for this course lets focus on commands we use very often. 

You'll find a reoccuring theme with `ls`, `inspect`, `rm`, `prune` which can be used in conjunction with many of Dockers objects. Here are some examples with resources we'll be learning about today.  

#### Images
- `docker image <ls or inspect or rm or prune>`
- `docker images` (list all images)
- `docker rmi <image-name>:<image-tag>` (remove image)

#### Containers
- `docker container <ls or inspect or rm or prune>`
- `docker ps -a` (list all regardless of state, without -a shows only running containers)

#### Networks
- `docker network <ls or inspect or rm or prune>`  

#### Volumes
- `docker volume <ls or inspect or rm or prune>`

## Single Stage
A simple implementation of a Node.js API. There are some useful things to note here though. We're doing some interesting volume mappings, notice there are 2 different startup commands (1 in the Dockerfile, 1 in the docker-compose.yaml) what does this mean? We're using `build: .` in the docker-compose.yaml, how does Docker interpret this?

## Multi-Stage

With multi-stage builds, you use multiple FROM statements in your Dockerfile. Each FROM instruction can use a different base, and each of them begins a new stage of the build. You can selectively copy artifacts from one stage to another, leaving behind everything you don’t want in the final image.

## Volumes

Volumes are the preferred mechanism for persisting data generated by and used by Docker containers. While bind mounts are dependent on the directory structure of the host machine, volumes are completely managed by Docker.

## Networking

One of the reasons Docker containers and services are so powerful is that you can connect them together, or connect them to non-Docker workloads. Docker containers and services do not even need to be aware that they are deployed on Docker, or whether their peers are also Docker workloads or not. Whether your Docker hosts run Linux, Windows, or a mix of the two, you can use Docker to manage them in a platform-agnostic way.

This topic defines some basic Docker networking concepts and prepares you to design and deploy your applications to take full advantage of these capabilities.