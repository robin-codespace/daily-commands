# Brief introduction about docker 

Docker is an open-source platform that automates the deployment, scaling, and management of 
application using containerization tehcnology. With docker, developers can package an application
with its dependencies, for example, libraries, framework and cofig files, into a single 
lightweight unit that can run across different platforms. 

## Dockerfile 
A Dockerfile is a recipe: it contains a set of instructions with which we tell Docker to build a 
cotainer image. It defines the environment, dependencies and configs needs to run an application
insider a Docker container. 

An example can be found [here](/docs/docker/Dockerfile).

## Docker Compose File 
A docker compose file is a YAML config file used with Docker Compose, a tool for defining and running 
multi-container Docker applications. It allows us to specify multiple services(containers), their config, 
networks and volumes etc in a single file, making it easier to manage complex application.
Instead of running multiple `docker run` manually, we can define everything in the `docker-compose.yml`
file and start all containers with a single command `docker-compose up`

An exampel about docker-compose file can be found [here](/docs/docker/docker-compose.yml).
## commands

### docker build 
- `docker build -t my-app:latest .` - build a docker image named `my-app` with a tag `latest` from 
a Dockerfile in the current directory `.`

- `docker run -p 8080:8080 --env-file .env my-app:latest` - run the docker image `my-app` with the `latest`
tag, map port `8080` from the local host to the exposed port in docker container. Inject environment variables
with `.env` file.

- `docker ps` - list running containers
- `docker image` - list all images
- `docker stop <container_id>` - stop a container
- `docker start <container_id>` - start a container
- `docker rm <container_id>` - remove a container
- `docker rmi <image_name>` - remove an image
- `docker logs <container_id>` - view logs of a container 
- `docker inspect <container_id>` - inspect a container, can combine for example `| grep Architecture`
- `docker-compose up` - starts all services (with `-d` to run in the background)
- `docker-compose down` - stops and removes containers, networks (volumes persists unless `-v` is added) 
- `docker-compose build` - builds or re-build images for service with a `build` section
- `docker-compose ls` - lists running services
- `docker-compose logs` - show logs for all services


## Interesting and Annoying facts

### Behaviour - 1 
I was tasked with configuring AWS ECS in which our service will be running as Fargate type. Part of the task configuration I had was 
```
runtimePlatform: {
    opeartingSystemFamily: OperatingSystemFamily.LINUX,
    cpuArchitecture: CpuArchitecture.X86_64
}
```
During the deployment, the task cannot up and running
### Error message
Only `exec /usr/bin/java: exec format error`

### Reason
The docker image's architecture is ARM64 because I have a MAC!! which is conflict with the architecture in the task definition

### Resolve
Run `export DOCKER_DEFAULT_PLATFORM='linux/amd64'`