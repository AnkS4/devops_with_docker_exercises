### Test Data Persistence with Docker Volumes in a Full-Stack Application (Postgres, Redis, Backend, Frontend)
```
$ docker compose up
[+] Running 5/5
 ✔ Network exercise27_default       Created                                                                                                                                                                                      0.3s 
 ✔ Container exercise27-db-1        Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-frontend-1  Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-redis-1     Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-backend-1   Created                                                                                                                                                                                      0.0s 
Attaching to backend-1, db-1, frontend-1, redis-1
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
frontend-1  |  INFO  Accepting connections at http://localhost:5000
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 16 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/css/main.eaa5d75e.chunk.css
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/2.43ca3586.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/main.667b6e84.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 9 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 6 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 10 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/media/toskalogo.c0f35cf0.svg
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 3 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /favicon.ico
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /manifest.json
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 3 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 4 ms
backend-1   | [GIN] [DATETIME] | 200 |     104.201µs |      x.x.x.x | GET      "/ping"
backend-1   | ping pong
backend-1   | [GIN] [DATETIME] | 200 |     220.164µs |      x.x.x.x | GET      "/ping?redis=true"
backend-1   | &{1 pong}
backend-1   | [GIN] [DATETIME] | 200 |    2.200829ms |      x.x.x.x | GET      "/ping?postgres=true"
backend-1   | [GIN] [DATETIME] | 200 |     2.55283ms |      x.x.x.x | POST     "/messages"
backend-1   | [GIN] [DATETIME] | 200 |    1.278851ms |      x.x.x.x | GET      "/messages"
backend-1   | [GIN] [DATETIME] | 200 |      7.1817ms |      x.x.x.x | POST     "/messages"
backend-1   | [GIN] [DATETIME] | 200 |    1.067858ms |      x.x.x.x | GET      "/messages"
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 2 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/css/main.eaa5d75e.chunk.css
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 3 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/2.43ca3586.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/js/main.667b6e84.chunk.js
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 4 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 5 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /static/media/toskalogo.c0f35cf0.svg
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 1 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /favicon.ico
frontend-1  |  HTTP  [DATETIME] x.x.x.x GET /manifest.json
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 2 ms
frontend-1  |  HTTP  [DATETIME] x.x.x.x Returned 304 in 4 ms
backend-1   | [GIN] [DATETIME] | 200 |      1.2029ms |      x.x.x.x | GET      "/messages"
Gracefully stopping... (press Ctrl+C again to force)
[+] Stopping 4/4
 ✔ Container exercise27-frontend-1  Stopped                                                                                                                                                                                      0.5s 
 ✔ Container exercise27-backend-1   Stopped                                                                                                                                                                                      0.4s 
 ✔ Container exercise27-db-1        Stopped                                                                                                                                                                                      0.3s 
 ✔ Container exercise27-redis-1     Stopped                                                                                                                                                                                      0.3s 

$ docker compose down
[+] Running 5/5
 ✔ Container exercise27-backend-1   Removed                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-frontend-1  Removed                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-db-1        Removed                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-redis-1     Removed                                                                                                                                                                                      0.0s 
 ✔ Network exercise27_default       Removed                                                                                                                                                                                      0.6s 

$ docker compose up
[+] Running 5/5
 ✔ Network exercise27_default       Created                                                                                                                                                                                      0.3s 
 ✔ Container exercise27-db-1        Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-redis-1     Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-frontend-1  Created                                                                                                                                                                                      0.0s 
 ✔ Container exercise27-backend-1   Created                                                                                                                                                                                      0.0s 
Attaching to backend-1, db-1, frontend-1, redis-1
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
frontend-1  |  INFO  Accepting connections at http://localhost:5000
backend-1   | [GIN] [DATETIME] | 200 |    1.333399ms |      x.x.x.x | GET      "/messages"
Gracefully stopping... (press Ctrl+C again to force)
[+] Stopping 4/4
 ✔ Container exercise27-backend-1   Stopped                                                                                                                                                                                      0.5s 
 ✔ Container exercise27-frontend-1  Stopped                                                                                                                                                                                      0.5s 
 ✔ Container exercise27-redis-1     Stopped                                                                                                                                                                                      0.3s 
 ✔ Container exercise27-db-1        Stopped                                                                                                                                                                                      0.2s

```
