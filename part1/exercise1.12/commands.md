### Navigate to the frontend project directory to build the Docker image and run it
```
$ cd ~/material-applications/example-frontend/
$ docker build . -t frontend-project && docker run -p 5000:5000 frontend-project
[+] Building 2.4s (11/11) FINISHED                                                                 docker:default
 => [internal] load build definition from Dockerfile                                                         0.0s
 => => transferring dockerfile: 1.32kB                                                                       0.0s
 => [internal] load metadata for docker.io/library/node:16                                                   2.3s
 => [internal] load .dockerignore                                                                            0.0s
 => => transferring context: 87B                                                                             0.0s
 => [1/6] FROM docker.io/library/node:16@sha256:f77a1aef2da8d83e45ec990f45df50f1a286c5fe8bbfb8c6e4246c63897  0.0s
 => [internal] load build context                                                                            0.0s
 => => transferring context: 1.21kB                                                                          0.0s
 => CACHED [2/6] WORKDIR /usr/src/app                                                                        0.0s
 => CACHED [3/6] COPY . .                                                                                    0.0s
 => CACHED [4/6] RUN npm install                                                                             0.0s
 => CACHED [5/6] RUN npm run build                                                                           0.0s
 => CACHED [6/6] RUN npm install -g serve                                                                    0.0s
 => exporting to image                                                                                       0.0s
 => => exporting layers                                                                                      0.0s
 => => writing image sha256:2e46a9db0f7dc9817ae1d0570b776d0a670b486a47b8a195f3d3e914ec709940                 0.0s
 => => naming to docker.io/library/frontend-project                                                          0.0s
 WARN  Checking for updates failed (use `--debug` to see full error)
 INFO  Accepting connections at http://localhost:5000
 HTTP  3/24/2025 4:02:40 PM 147.83.203.164 GET /
 HTTP  3/24/2025 4:02:40 PM 147.83.203.164 Returned 304 in 49 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/css/main.eaa5d75e.chunk.css
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/js/2.43ca3586.chunk.js
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/js/main.1be634bd.chunk.js
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 304 in 6 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 304 in 6 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 304 in 9 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/css/main.eaa5d75e.chunk.css.map
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 200 in 4 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/media/toskalogo.c0f35cf0.svg
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/js/2.43ca3586.chunk.js.map
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /static/js/main.1be634bd.chunk.js.map
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 304 in 7 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 200 in 9 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 200 in 21 ms
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 GET /favicon.ico
 HTTP  3/24/2025 4:02:41 PM 147.83.203.164 Returned 304 in 2 ms
```
