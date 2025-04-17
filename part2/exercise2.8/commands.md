### Test Data Persistence with Docker Volumes in a Full-Stack Application (Postgres, Redis, Backend, Frontend)
```
$ docker compose up
[+] Running 6/6
 ✔ Network exercise28_default       Created                                                                                                                                                                                      0.2s 
 ✔ Container exercise28-redis-1     Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise28-db-1        Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise28-frontend-1  Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise28-backend-1   Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise28-proxy-1     Created                                                                                                                                                                                      0.0s 
Attaching to backend-1, db-1, frontend-1, proxy-1, redis-1
redis-1     | 1:C [DATETIME] # WARNING Memory overcommit must be enabled! Without it, a background save or replication may fail under low memory condition. Being disabled, it can also cause failures without low memory condition, see https://github.com/jemalloc/jemalloc/issues/1328. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
redis-1     | 1:C [DATETIME] * oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
redis-1     | 1:C [DATETIME] * Redis version=7.4.2, bits=64, commit=00000000, modified=0, pid=1, just started
redis-1     | 1:C [DATETIME] # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
redis-1     | 1:M [DATETIME] * Increased maximum number of open files to 10032 (it was originally set to 1024).
redis-1     | 1:M [DATETIME] * monotonic clock: POSIX clock_gettime
redis-1     | 1:M [DATETIME] * Running mode=standalone, port=6379.
redis-1     | 1:M [DATETIME] * Server initialized
redis-1     | 1:M [DATETIME] * Ready to accept connections tcp
db-1        | 
db-1        | PostgreSQL Database directory appears to contain a database; Skipping initialization
db-1        | 
db-1        | [DATETIME] UTC [1] LOG:  starting PostgreSQL 17.4 (Debian 17.4-1.pgdg120+2) on x86_64-pc-linux-gnu, compiled by gcc (Debian 12.2.0-14) 12.2.0, 64-bit
db-1        | [DATETIME] UTC [1] LOG:  listening on IPv4 address "x.x.x.x", port 5432
db-1        | [DATETIME] UTC [1] LOG:  listening on IPv6 address "::", port 5432
db-1        | [DATETIME] UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
db-1        | [DATETIME] UTC [29] LOG:  database system was shut down at [DATETIME] UTC
db-1        | [DATETIME] UTC [1] LOG:  database system is ready to accept connections
backend-1   | [Ex 2.4+] Initializing redis client
backend-1   | [Ex 2.4+] Connection to redis initialized, ready to ping pong.
backend-1   | [Ex 2.6+] Initializing postgres connection with envs
backend-1   |           POSTGRES_HOST      db,
backend-1   |           POSTGRES_USER:     postgres,
backend-1   |           POSTGRES_PASSWORD: postgres,
backend-1   |           POSTGRES_DATABASE: postgres
backend-1   |           to db:5432
db-1        | [DATETIME] UTC [33] ERROR:  relation "messages" already exists
db-1        | [DATETIME] UTC [33] STATEMENT:  CREATE TABLE "messages" ("id" bigserial, "body" text, PRIMARY KEY ("id"))
backend-1   | [Ex 2.6+] Connection to postgres initialized, ready to ping pong.
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
proxy-1     | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
proxy-1     | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
proxy-1     | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
proxy-1     | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
proxy-1     | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
proxy-1     | /docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
proxy-1     | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
proxy-1     | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
proxy-1     | /docker-entrypoint.sh: Configuration complete; ready for start up
frontend-1  |  INFO  Accepting connections at http://localhost:5000
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /
proxy-1     | x.x.x.x - - [[DATETIME]] "GET / HTTP/1.1" 304 0 "-" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 36 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/css/main.eaa5d75e.chunk.css
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/2.43ca3586.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/main.667b6e84.chunk.js
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /static/css/main.eaa5d75e.chunk.css HTTP/1.1" 304 0 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 12 ms
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /static/js/main.667b6e84.chunk.js HTTP/1.1" 304 0 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 9 ms
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /static/js/2.43ca3586.chunk.js HTTP/1.1" 304 0 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 16 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/media/toskalogo.c0f35cf0.svg
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /static/media/toskalogo.c0f35cf0.svg HTTP/1.1" 304 0 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 4 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /favicon.ico
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /manifest.json
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /favicon.ico HTTP/1.1" 304 0 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 6 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 8 ms
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /manifest.json HTTP/1.1" 304 0 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
backend-1   | [GIN] [DATETIME] | 200 |     134.372µs |      x.x.x.x | GET      "/ping"
proxy-1     | x.x.x.x - - [[DATETIME]] "GET /api/ping HTTP/1.1" 200 4 "http://localhost/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36"
```
