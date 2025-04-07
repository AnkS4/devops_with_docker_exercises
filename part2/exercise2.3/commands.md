### Run multi container app with docker compose
```
$ docker compose up
[+] Running 2/2
 ✔ Container exercise23-frontend-1  Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise23-backend-1   Created                                                                                                                                                                                      0.0s 
Attaching to backend-1, frontend-1
backend-1   | [Ex 2.4+] REDIS_HOST env was not passed so redis connection is not initialized
backend-1   | [Ex 2.6+] POSTGRES_HOST env was not passed so postgres connection is not initialized
backend-1   | [GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.
backend-1   | 
backend-1   | [GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
backend-1   |  - using env:     export GIN_MODE=release
backend-1   |  - using code:    gin.SetMode(gin.ReleaseMode)
backend-1   | 
backend-1   | [GIN-debug] GET    /ping                     --> server/router.pingpong (4 handlers)
backend-1   | [GIN-debug] GET    /messages                 --> server/controller.GetMessages (4 handlers)
backend-1   | [GIN-debug] POST   /messages                 --> server/controller.CreateMessage (4 handlers)
backend-1   | [GIN-debug] Listening and serving HTTP on :8080
frontend-1  |  INFO  Accepting connections at http://localhost:5000
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 19 ms
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /static/css/main.eaa5d75e.chunk.css
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /static/js/2.43ca3586.chunk.js
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /static/js/main.667b6e84.chunk.js
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 14 ms
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 10 ms
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 17 ms
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /static/media/toskalogo.c0f35cf0.svg
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 2 ms
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /favicon.ico
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 GET /manifest.json
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 2 ms
frontend-1  |  HTTP  4/7/2025 01:09:20 AM 172.19.0.1 Returned 304 in 2 ms
backend-1   | [GIN] 2025/04/07 - 01:09:24 | 200 |     122.715µs |      172.19.0.1 | GET      "/ping"
Gracefully stopping... (press Ctrl+C again to force)
[+] Stopping 2/2
 ✔ Container exercise23-frontend-1  Stopped                                                                                                                                                                                      0.4s 
 ✔ Container exercise23-backend-1   Stopped 
```
