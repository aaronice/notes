# Best practices and Reference for Dockerfiles


- [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
- [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)


Define a container with `Dockerfile`

Then build an image from a Dockerfile

```
$ docker build
```


Docker Commands

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



```