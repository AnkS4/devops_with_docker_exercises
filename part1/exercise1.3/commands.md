### Run a Docker container in detached mode with the name 'exer' using the ubuntu version of simple-web-service
```
$ docker run -d --name exer devopsdockeruh/simple-web-service:ubuntu
1686747a8e71ba4a9c66dd0f3f2a7bc0a561b03038aed01329a3fd81a529b713
```

### Execute an interactive command inside the running container to view the log file
#### The -it flag allows for interactive terminal access
#### tail -f continuously follows the log file as it's updated
```
$ docker exec -it exer tail -f ./text.log
2025-03-19 16:47:46 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2025-03-19 16:47:48 +0000 UTC
2025-03-19 16:47:50 +0000 UTC
2025-03-19 16:47:52 +0000 UTC
2025-03-19 16:47:54 +0000 UTC
2025-03-19 16:47:56 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
^C  # Command was terminated with Ctrl+C
```
