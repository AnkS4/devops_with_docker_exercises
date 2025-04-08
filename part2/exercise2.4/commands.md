### Start a multi-container application with Redis, backend, and frontend services using docker compose
```
$ docker compose up
[+] Running 9/9
 ✔ redis Pulled                                                                                                                                                                                                                  3.2s 
   ✔ f18232174bc9 Already exists                                                                                                                                                                                                 0.0s 
   ✔ 16cd0457255f Pull complete                                                                                                                                                                                                  0.4s 
   ✔ fa05f5234346 Pull complete                                                                                                                                                                                                  0.6s 
   ✔ 4d03bd351ab9 Pull complete                                                                                                                                                                                                  0.6s 
   ✔ 4738865c5f32 Pull complete                                                                                                                                                                                                  1.5s 
   ✔ 927ba88b2847 Pull complete                                                                                                                                                                                                  1.5s 
   ✔ 4f4fb700ef54 Pull complete                                                                                                                                                                                                  1.5s 
   ✔ 4c7f0522bc7d Pull complete                                                                                                                                                                                                  1.5s 
[+] Running 4/4
 ✔ Network exercise24_default       Created                                                                                                                                                                                      0.2s 
 ✔ Container exercise24-backend-1   Created                                                                                                                                                                                      0.1s 
 ✔ Container exercise24-frontend-1  Created                                                                                                                                                                                      0.1s 
 ✔ Container exercise24-redis-1     Created                                                                                                                                                                                      0.0s 
Attaching to backend-1, frontend-1, redis-1
redis-1     | 1:C xx xxx xxxx xx:xx:xx.xxx * oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
redis-1     | 1:C xx xxx xxxx xx:xx:xx.xxx * Redis version=7.4.2, bits=64, commit=00000000, modified=0, pid=1, just started
redis-1     | 1:C xx xxx xxxx xx:xx:xx.xxx # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
redis-1     | 1:M xx xxx xxxx xx:xx:xx.xxx * Increased maximum number of open files to 10032 (it was originally set to 1024).
redis-1     | 1:M xx xxx xxxx xx:xx:xx.xxx * monotonic clock: POSIX clock_gettime
redis-1     | 1:M xx xxx xxxx xx:xx:xx.xxx * Running mode=standalone, port=6379.
redis-1     | 1:M xx xxx xxxx xx:xx:xx.xxx * Server initialized
redis-1     | 1:M xx xxx xxxx xx:xx:xx.xxx * Ready to accept connections tcp
backend-1   | [Ex 2.4+] Initializing redis client
backend-1   | [Ex 2.4+] Connection to redis initialized, ready to ping pong.
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
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 23 ms
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /static/css/main.eaa5d75e.chunk.css
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /static/js/2.43ca3586.chunk.js
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /static/js/main.667b6e84.chunk.js
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 12 ms
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 6 ms
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 13 ms
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /static/media/toskalogo.c0f35cf0.svg
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 2 ms
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /favicon.ico
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x GET /manifest.json
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 5 ms
frontend-1  |  HTTP  x/x/xxxx x:xx:xx xx x.x.x.x Returned 304 in 6 ms
backend-1   | ping pong
backend-1   | [GIN] xxxx/xx/xx - xx:xx:xx | 200 |     678.554µs |      x.x.x.x | GET      "/ping?redis=true"
Gracefully stopping... (press Ctrl+C again to force)
[+] Stopping 3/3
 ✔ Container exercise24-frontend-1  Stopped                                                                                                                                                                                      0.4s 
 ✔ Container exercise24-redis-1     Stopped                                                                                                                                                                                      0.2s 
 ✔ Container exercise24-backend-1   Stopped
```
