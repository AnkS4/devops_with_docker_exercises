### Run Docker Compose Application using compose command
```
$ docker compose up
[+] Running 1/1
 ✔ Container simple-web-browser-web-1  Created                                                               0.0s
Attaching to web-1
web-1  | [GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.
web-1  | 
web-1  | [GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
web-1  |  - using env:  export GIN_MODE=release
web-1  |  - using code: gin.SetMode(gin.ReleaseMode)
web-1  | 
web-1  | [GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
web-1  | [GIN-debug] Listening and serving HTTP on :8080
web-1  | [GIN] 2025/04/06 - 14:24:10 | 200 |     103.421µs |  x.x.x.x | GET      "/"
Gracefully stopping... (press Ctrl+C again to force)
[+] Stopping 1/1
 ✔ Container simple-web-browser-web-1  Stopped

```

### Test API Endpoint using curl
```
$ curl http://x.x.x.x:8000
{"message":"You connected to the following path: /","path":"/"}
```
