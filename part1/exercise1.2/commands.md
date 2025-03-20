### Stop all the containers
```
$ docker stop wonderful_ramanujan
wonderful_ramanujan
```

### Clean the Docker daemon by removing all images and containers
```
$ docker rm keen_austin hungry_lalande wonderful_ramanujan
keen_austin
hungry_lalande
wonderful_ramanujan
```

### Verify the container and image listings
```
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

$ docker image ls
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
```
