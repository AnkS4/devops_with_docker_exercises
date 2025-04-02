### Navigate to the backend project directory to build the Docker image and run it
```
$ cd ~/material-applications/example-backend/
$ docker build . -t backend-project && docker run -p 8080:8080 backend-project
[+] Building 0.5s (9/9) FINISHED                                                                    docker:default
 => [internal] load build definition from Dockerfile                                                          0.0s
 => => transferring dockerfile: 187B                                                                          0.0s
 => [internal] load metadata for docker.io/library/golang:1.24                                                0.4s
 => [internal] load .dockerignore                                                                             0.0s
 => => transferring context: 111B                                                                             0.0s
 => [1/4] FROM docker.io/library/golang:1.24@sha256:52ff1b35ff8de185bf9fd26c70077190cd0bed1e9f16a2d498ce907e  0.0s
 => => resolve docker.io/library/golang:1.24@sha256:52ff1b35ff8de185bf9fd26c70077190cd0bed1e9f16a2d498ce907e  0.0s
 => [internal] load build context                                                                             0.0s
 => => transferring context: 499B                                                                             0.0s
 => CACHED [2/4] WORKDIR /usr/src/app                                                                         0.0s
 => CACHED [3/4] COPY . .                                                                                     0.0s
 => CACHED [4/4] RUN go build                                                                                 0.0s
 => exporting to image                                                                                        0.0s
 => => exporting layers                                                                                       0.0s
 => => writing image sha256:638b7982ee58d9eb0554486e9c6119df5599ef85f99ca99aa6ce1e07558f07bd                  0.0s
 => => naming to docker.io/library/backend-project                                                            0.0s
[Ex 2.4+] REDIS_HOST env was not passed so redis connection is not initialized
[Ex 2.6+] POSTGRES_HOST env was not passed so postgres connection is not initialized
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:   export GIN_MODE=release
 - using code:  gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /ping                     --> server/router.pingpong (4 handlers)
[GIN-debug] GET    /messages                 --> server/controller.GetMessages (4 handlers)
[GIN-debug] POST   /messages                 --> server/controller.CreateMessage (4 handlers)
[GIN-debug] Listening and serving HTTP on :8080
[GIN] 2025/03/24 - 16:09:16 | 404 |     126.985µs |  147.83.203.164 | GET      "/"
[GIN] 2025/03/24 - 16:09:16 | 403 |      50.616µs |  147.83.203.164 | GET      "/favicon.ico"
[GIN] 2025/03/24 - 16:09:16 | 404 |       7.645µs |  147.83.203.164 | GET      "/favicon.ico"
```
