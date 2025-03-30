### Run the Docker container with port mapping and server command
```
$ docker run -p 8080:8080 devopsdockeruh/simple-web-service server
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:   export GIN_MODE=release
 - using code:  gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
[GIN-debug] Listening and serving HTTP on :8080
[GIN] 2025/03/21 - 16:05:58 | 200 |     142.067µs |  147.83.203.164 | GET      "/"
[GIN] 2025/03/21 - 16:05:58 | 200 |     100.185µs |  147.83.203.164 | GET      "/favicon.ico"
```

### Access the contents with your browser in http://localhost:8080
```
{"message":"You connected to the following path: /","path":"/"}
```
