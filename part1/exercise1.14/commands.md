### Navigate to the frontend project directory to build the Docker image and run it
```
$ cd ~/material-applications/example-frontend/
$ docker build . -t frontend-project && docker run -p 5000:5000 frontend-project
[+] Building 120.7s (11/11) FINISHED                                                               docker:default
 => [internal] load build definition from Dockerfile                                                         0.0s
 => => transferring dockerfile: 1.46kB                                                                       0.0s
 => [internal] load metadata for docker.io/library/node:16                                                   4.7s
 => [internal] load .dockerignore                                                                            0.0s
 => => transferring context: 87B                                                                             0.0s
 => [1/6] FROM docker.io/library/node:16@sha256:f77a1aef2da8d83e45ec990f45df50f1a286c5fe8bbfb8c6e4246c63897  0.0s
 => [internal] load build context                                                                            0.0s
 => => transferring context: 1.21kB                                                                          0.0s
 => CACHED [2/6] WORKDIR /usr/src/app                                                                        0.0s
 => CACHED [3/6] COPY . .                                                                                    0.0s
 => [4/6] RUN npm install                                                                                   65.1s
 => [5/6] RUN npm run build                                                                                 25.4s
 => [6/6] RUN npm install -g serve                                                                           3.8s
 => exporting to image                                                                                      21.6s
 => => exporting layers                                                                                     21.5s
 => => writing image sha256:a8e7eb3caf660e88c3aaf9d9e8f16af7f17842c29d4341db760b8c6bccc08ed6                 0.0s
 => => naming to docker.io/library/frontend-project                                                          0.0s
 INFO  Accepting connections at http://localhost:5000
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 200 in 32 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/js/main.e42fea1c.chunk.js
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/css/main.eaa5d75e.chunk.css
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/js/2.43ca3586.chunk.js
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 200 in 8 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 304 in 7 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 304 in 10 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/css/main.eaa5d75e.chunk.css.map
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 304 in 3 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/js/2.43ca3586.chunk.js.map
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 304 in 8 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/media/toskalogo.c0f35cf0.svg
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 304 in 3 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /static/js/main.e42fea1c.chunk.js.map
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 200 in 4 ms
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 GET /favicon.ico
 HTTP  3/25/2025 9:27:27 AM 147.83.203.164 Returned 200 in 3 ms
^C
 INFO  Gracefully shutting down. Please wait...
```

### Navigate to the backend project directory to build the Docker image and run it
```
$ cd ~/material-applications/example-backend/
$ docker build . -t backend-project && docker run -p 8080:8080 backend-project
[+] Building 32.1s (9/9) FINISHED                                                                   docker:default
 => [internal] load build definition from Dockerfile                                                          0.0s
 => => transferring dockerfile: 657B                                                                          0.0s
 => [internal] load metadata for docker.io/library/golang:1.24                                                1.4s
 => [internal] load .dockerignore                                                                             0.0s
 => => transferring context: 111B                                                                             0.0s
 => [internal] load build context                                                                             0.0s
 => => transferring context: 499B                                                                             0.0s
 => [1/4] FROM docker.io/library/golang:1.24@sha256:52ff1b35ff8de185bf9fd26c70077190cd0bed1e9f16a2d498ce907e  0.0s
 => => resolve docker.io/library/golang:1.24@sha256:52ff1b35ff8de185bf9fd26c70077190cd0bed1e9f16a2d498ce907e  0.0s
 => CACHED [2/4] WORKDIR /usr/src/app                                                                         0.0s
 => CACHED [3/4] COPY . .                                                                                     0.0s
 => [4/4] RUN go build                                                                                       25.8s
 => exporting to image                                                                                        4.8s 
 => => exporting layers                                                                                       4.8s 
 => => writing image sha256:92d25ff79af77cf8efde631fb7843d08c3870aaf91546338f987ef03060c0bf4                  0.0s 
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
[GIN] 2025/03/25 - 09:27:28 | 200 |     130.702µs |  147.83.203.164 | GET      "/ping"
^C
```
