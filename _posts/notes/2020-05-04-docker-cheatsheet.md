---
title: "Docker Cheatsheet"
date: "2020-05-04"
draft: false
tags: ["containerization", "docker", "cheatsheet"]
---

### Commands
---
```shell
# pull images
$ docker pull busybox
```


```shell
# run an image/ finds no command / gets exited
$ docker run busybox
```

```shell
# containers are fast / getting into vm doing this and exiting (slow)
$ docker run busybox echo "hello from busybox"
```

```shell
# all containers that are running
$ docker ps
```

```shell
# all containers that ran
$ docker ps -a
```

```shell
# attaches the interavtive shell
$ docker run -it busybox sh
```

``` shell
# removes the container when it exits
$ docker run --rm prakhar1989/static-site
```
- `--rm` flag  automatically removes the container when it exits

```shell
$ docker run -d -P --name static-site prakhar1989/static-site
```
- keep the container running providing name to it
- `-d` will detach the terminal `-P` publish the ports `--name` desired name for the container

```shell
# ports
$ docker port [CONTAINER --name]
```
- see the ports [ only after publishing the ports with `-P`]

```shell
# copy from container
$ docker cp <containerId>:/file/path/within/container /host/path/target
```
- copy from docker container

```shell
# stop container
$ docker stop static-site
```
- stop the container
---

### Somehow messed up and start from scratch?

```shell
# remove all docker containers
$ docker rm $(docker ps -a -q) -f
```
- remove all docker containers

```shell
# remove all docker images
$ docker rmi $(docker images) -f
```
- remove all docker images

### Some Docker Terminologies
---

##### images
- docker pull command to download the busybox image

##### containers
- created from docker images and run the actual application

##### docker daemon
- background service running on the host(locally your pc or anything that the docker is running) that manages building, running and distributing docker
  containers.

##### docker client
- cli tool that allows (me) to interact with the daemon
- GUI clients - Kitematic

##### docker hub
- a registry of docker images / directory of all the available docker images

### Docker Images
---
- basis of containers
- `$ docker images` to view images locally
- `$ docker search python` to search for images
- images (like git repos)
    - can have multuple versions
    - if not provided picks latest version
    - `$ docker pull ubuntu:18.04`

### Docker Expose
---
- 8000:5000
- local host-port ->> 8000:5000 <<- run docker container

- `$ docker run -p 8888:80 new-site`
- `-P` expose random ports on the container
    - `$ docker port [Container_name]` -> to view the allocated ports
- `-p` provide port on local and container env [8000:5000]
- container port `5000` to be available on your localhost `8000`, you need to specify:
    - `$ docker run -p localhost:8000:5000` # and so on

---

#### Docker Compose cheatsheet

https://devhints.io/docker-compose

- remove docker containers (not active)
    - `$ docker rm (docker ps -a -q) -f`
- remove hanging images
    - `$ docker rmi (docker images -f dangling=true -q)`
- docker compose up --build again
    - `$ docker-compose up --build again`
- remove all the images from repository name
    - `docker rmi $(docker images -q ubuntu)`

---

#### Thrive to minimize image size

---

#### Docker multi-stage build
https://docs.docker.com/develop/develop-images/multistage-build/
```Dockerfile
# single docker file could be used for multiple stage builds...

# for example:

FROM python:3.6-alpine as dev-build
# -
# -
# -
# -
# -

# --------

FROM python:3.6-alpine as prod-build

# this app includes the dist and all the necessary build files (in case of js)
COPY --from=dev-build /app/ .

# -
# -
# -
# -
# -
```

### Stopping at a specific build stage

It's not necessary for Dockerfile to run all at once...
- `$ docker build --target dev-build -t sisir/django-app:latest .`


### Use a previous stage as a new stage
```Dockerfile
FROM alpine:latest as builder
RUN apk --no-cache add build-base

FROM builder as build1
COPY source1.cpp source.cpp
RUN g++ -o /binary source.cpp

FROM builder as build2
COPY source2.cpp source.cpp
RUN g++ -o /binary source.cpp
```

- Docker compose allows to configure multi-container app.

### Container Vs. Entrypoint

https://phoenixnap.com/kb/docker-cmd-vs-entrypoint
