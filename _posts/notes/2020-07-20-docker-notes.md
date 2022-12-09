---
title: "Docker Notes"
date: 2020-07-20
draft: false
tags: ["docker"]
---

### A Brief History Of The Shipping Industry (DOCKER)
---
- loading and unloading of goods in barrel, sacks and wooden crate from land transporters to ship
and back again on arrival.
- this process: `break-bulk shipping` was the only known way to transport goods until the 20th
  century. slow and cumbersome.
- then came dockers


### What problem docker is solving?
---
- Keep Your Computers Tidy with Containers (locally)
- When someone sends you a Java App, is the JVM installed? What about runtime libraries?
What about additional libraries? Where does the App Begin and End?
Docker solved for answering that question predictably, accurately, portably and conclusively.
[ref taken]
- run a piece of software in isolation from the rest of the system  (making clean everything)
- kind of resembles to python virtual environments

### VM and Container
---
Similar to a VM, a container has its own filesystem, CPU, memory, process space, and more.

### Benefits of Container
---
- increased ease and efficiency of container image creation compared to VM image use.
- Dev and Ops separation of concerns
- Environmental consistency across development, testing, and production: Runs the same on a laptop as it does in the cloud.


### Docker Compose vs. Dockerfile

| docker-compose                                    | dockerfile                                     |
|:--------------------------------------------------|:------------------------------------------------|
| - compose whole application services              | - used for single service                      |
| - docker-compose.yml                              | - Dockerfile                                   |
| - deploy entire stack with docker compose command | - create useful containers (might be reusable) |
|||


* Dockerfile
    - create dockerfile to build images
* Docker Compose
    - used for defining and running multi-container Docker applications


`Which one to use? Best of two worlds...`
- make use of both dockerfile and docker-compose


### docker container vs image
---

| docker image                                                                  | docker container                                           |
|-------------------------------------------------------------------------------|------------------------------------------------------------|
| - set of layers                                                               | - if we have the running instance of the image = container |
| - packs up the application and environment required by the application to run | - analogous to "process"                                   |
| - ubuntu image, python image                                                  |                                                            |
| - `$ docker images` --lists all images locally                                | - `$ docker ps` -- lists all the running containers        |
| - OOP: Image is equivalent to Class                                           | - `$ docker ps -a` -- lists all the containers that ran    |
| - layers are different methods and set of properties                          | - OOP: container is the actual instantiation of the image  |
|                                                                               |                                                            |
* Running instance of an image = contianer


### Docker run with flask app
---

`running from dockerfile`
- first build an image with -t tag and then only run
- couldn't found the way to run from Dockerfile directly, first need to build and then run the image
as a container

### Networking using the Host Network
---
- The host networking driver only works on Linux hosts, and is,
- `not supported on Docker Desktop for Mac`, Docker Desktop for Windows, or Docker EE for Windows Server.

### Docker Dev
---
- running mysql dev locally.

- // goto local docker compose

`$ docker-compose up -d`
detach the container

`$ docker exec -it mysql-dev /bin/bash`
run shell on mysql-dev

`$ docker exec -it c0f6543a8f36 /bin/sh -c "printenv"`
run particular command

### Docker Engines
---

- Docker Engine Swarm Mode (Kubernetes alternative by Docker)
    - cluster of docker engines
    - addings nodes to the swarm
    - deploying application services to the swarm
    - managing the swarm after everything is running

* Docker Desktop for Mac
    - You can test both single-node and multi-node swarm from this computer, but you need to use
    - `Docker Machine` to test the multi-node scenarios.

### Docker Network
---

`$ docker network create -d bridge mynet`
- creating a docker network

### Kubernetes
---
- The technical definition of orchestration is execution of a defined workflow: first do A, then B, then C.

### Docker Compose
- write docker-compose.yml
- `$ docker-compose up`

* volumes:
    - Mounting volumes enables us to map local source code to the corresponding code in the container,
    so that every time we edit these code files in our local the changes will be instantly reflected in the
    container.
- Docker compose what is link?

##### docker-compose commands

`$ docker-compose up -d`
detach docker compose

`$ docker-compose ps`
docker-compose processes

`$ docker-compose stop`
stop the services


### Dockerfile run / cmd / entry point?
| RUN                                                                             | CMD                                                      | ENTRY POINT |
|---------------------------------------------------------------------------------|----------------------------------------------------------|-------------|
| when running the commands for creating the layer in the docker: use run command | runs each and everytime when docker container is running | -           |
|||

script - entry point how to run?

### docker mysql local dev
---

- `$ docker run -p 3304:3306 --name mysql-local -e  MYSQL_ROOT_PASSWORD=toor -d mysql:latest`
