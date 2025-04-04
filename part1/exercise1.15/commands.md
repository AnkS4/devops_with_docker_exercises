## Build the Docker image and run it
```
$ docker build . -t alpine-snake && docker run -it alpine-snake
[+] Building 1.6s (9/9) FINISHED                                                                   docker:default
 => [internal] load build definition from Dockerfile                                                         0.0s
 => => transferring dockerfile: 170B                                                                         0.0s
 => [internal] load metadata for docker.io/library/alpine:3.21                                               1.6s
 => [auth] library/alpine:pull token for registry-1.docker.io                                                0.0s
 => [internal] load .dockerignore                                                                            0.0s
 => => transferring context: 2B                                                                              0.0s
 => [1/4] FROM docker.io/library/alpine:3.21@sha256:a8560b36e8b8210634f77d9f7f9efd7ffa463e380b75e2e74aff451  0.0s
 => CACHED [2/4] WORKDIR /usr/src/app                                                                        0.0s
 => CACHED [3/4] RUN apk update && apk upgrade                                                               0.0s
 => CACHED [4/4] RUN apk add bsd-games                                                                       0.0s
 => exporting to image                                                                                       0.0s
 => => exporting layers                                                                                      0.0s
 => => writing image sha256:f9db57d424fb164fd8f2ee6e8697e7defe322e7996b148ef65c4931909a33462                 0.0s
 => => naming to docker.io/library/alpine-snake                                                              0.0s
```

## Verify if containers is listed
```
$ docker ps -a | grep snake
d08615c82e15   alpine-snake                               "snake"                  52 seconds ago   Exited (0) 49 seconds ago             youthful_wiles                                                                            │
```

## Tag & push the image for Docker Hub
```
$ docker tag alpine-snake anks0/alpine-snake
$ docker push anks0/alpine-snake
Using default tag: latest
The push refers to repository [docker.io/anks0/alpine-snake]
83be682c0492: Pushed
91ef642c5dee: Pushed
a16995c1c378: Pushed
08000c18d16d: Mounted from library/alpine
latest: digest: sha256:485ddf683cfb889d671f7dd8f71f2d0b1aee057f1ad4f4453c32f3f9dbc9c0ec size: 1156
```
