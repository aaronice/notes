# Notes and Tips on Docker Container




## Best practices for Dockerfiles


- [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
- [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)


`Dockerfile` defines a container 

Then build an image from a Dockerfile

```
$ docker build
```


## Commonly Used Docker Commands

```

// List all containers
$ docker ps -a 

// List stopped containers
$ docker ps -f "status=exited"

// Remove all stopped containers
$ docker rm $(docker ps -a -q)

// List Docker images
$ docker images

REPOSITORY                TAG                 IMAGE ID            CREATED             SIZE
test1                     latest              fd484f19954f        23 seconds ago      7 B (virtual 4.964 MB)
test                      latest              fd484f19954f        23 seconds ago      7 B (virtual 4.964 MB)
test2                     latest              fd484f19954f        23 seconds ago      7 B (virtual 4.964 MB)

// Remove a docker images by id
$ docker rmi fd484f19954f

// Create a new image from a container’s changes
$ docker commit a5f2a390c452 ssm-env

// Launch several sessions connected to the same container 
// from multiple host terminals.
$ docker exec -it <container> bash

```