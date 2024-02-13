# Docker cheatsheet

- [Video guide](https://www.youtube.com/watch?v=3c-iBn73dDE) for general Docker knowledge.

## Table of contents

<!-- vim-markdown-toc GFM -->

- [Images](#images)
- [Container](#container)
- [Networking](#networking)
- [Run command](#run-command)
- [Docker Compose](#docker-compose)

<!-- vim-markdown-toc -->

## Images

- List Docker images in the system

```bash
$ docker images
```

- Build an image from a Dockerfile

```bash
$ docker build -t <IMAGE_NAME:VERSION> <DOCKERFILE_PATH>

-t:		Tag for the image, e.g. 'app:1.1.2'

e.g.: docker build -t test:0.1.0 .
```

- Pull image from repository

```bash
$ docker pull <IMAGE_NAME>
```

- Delete an image locally from Docker

```bash
$ docker rmi <IMAGE_ID/IMAGE_NAME>
```

- Rename an image

```bash
$ docker tag <CURRENT_IMAGE_NAME:VERSION> <NEW_IMAGE_NAME:VERSION>
```

## Container

- Show containers currently running in the system

```bash
$ docker ps
```

- Show the logs of a particular container

```bash
$ docker logs <CONTAINER_ID/CONTAINER_NAME>
```

- Show all running and stopped containers in the system

```bash
$ docker ps -a
```

- Delete a container

```bash
$ docker rm <CONTAINER_ID/CONTAINER_NAME>
```

- Run an interactive shell inside a running container

```bash
$ docker exec -it <CONTAINER_ID/CONTAINER_NAME> /bin/sh
```

## Networking

- Show all current Docker networks

```bash
$ docker network ls
```

- Create a Docker network

```bash
$ docker network create <NAME_NETWORK>
```

- Delete a Docker network

```bash
$ docker network rm <NAME OF NETWORK>
```

- Delete all unused networks (`prune`)

```bash
$ docker network prune
```

## Run command

- Important flags for `docker run` command:

```bash
--net:		Specify the network to which the container will be connected
--rm:		Remove container automatically after it has been stopped.

```

## Docker Compose

- Run a specific Docker Compose YAML file

```bash
$ docker-compose -f <YAML-File> up
```

- Run a specific Docker Compose YAML file in detached-mode

```bash
$ docker-compose -f <YAML-File> up -d
```

- Stop the containers previously initialized with a Docker Compose file

```bash
$ docker-compose -f <YAML-File> down
```
