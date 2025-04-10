### Start a Multi-Container Application with Postgres, Redis, Backend, and Frontend Services Using Docker Compose
```
$ docker compose up
[+] Running 3/3
 ✔ Container exercise26-db-1       Running                                                                                                                                                                                       0.0s 
 ✔ Container exercise26-redis-1    Running                                                                                                                                                                                       0.0s 
 ✔ Container exercise26-backend-1  Running                                                                                                                                                                                       0.0s 
Attaching to backend-1, db-1, frontend-1, redis-1
frontend-1  |  INFO  Accepting connections at http://localhost:5000
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 27 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/css/main.eaa5d75e.chunk.css
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/2.43ca3586.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/main.667b6e84.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 3 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 3 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 5 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/media/toskalogo.c0f35cf0.svg
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 2 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /manifest.json
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /favicon.ico
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 3 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 6 ms
backend-1   | [GIN] [DATETIME] | 200 |     315.752µs |      x.x.x.x | GET      "/ping"
backend-1   | ping pong
backend-1   | [GIN] [DATETIME] | 200 |     476.526µs |      x.x.x.x | GET      "/ping?redis=true"
```
