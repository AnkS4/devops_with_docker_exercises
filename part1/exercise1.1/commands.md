### Start 3 containers from an image that does not automatically exit (such as nginx) in detached mode

```
$ docker run -d nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
6e909acdb790: Pull complete
5eaa34f5b9c2: Pull complete
417c4bccf534: Pull complete
e7e0ca015e55: Pull complete
373fe654e984: Pull complete
97f5c0f51d43: Pull complete
c22eb46e871a: Pull complete
Digest: sha256:124b44bfc9ccd1f3cedf4b592d4d1e8bddb78b51ec2ed5056c52d3692baebc19
Status: Downloaded newer image for nginx:latest
443f3b8cae04f8c337bc2840ccf36f178c708e61bd04c78cb5ba58a787666d45

$ docker run -d nginx
fc47647cf7d1954f8738b530fbf7d77ffeecadca79838ed003671c3e6b41c29a

$ docker run -d nginx
054514cef06718f77e3d980685026d9391249c7188454e048af30b4534e17989

$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS     NAMES
054514cef067   nginx     "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   80/tcp    keen_austin
fc47647cf7d1   nginx     "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   80/tcp    hungry_lalande
443f3b8cae04   nginx     "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   80/tcp    wonderful_ramanujan
```

### Stop two of the containers

```
$ docker stop keen_austin
keen_austin
$ docker stop fc4
fc4
```

### List all the containers
```
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
054514cef067   nginx     "/docker-entrypoint.…"   4 minutes ago    Exited (0) 23 seconds ago             keen_austin
fc47647cf7d1   nginx     "/docker-entrypoint.…"   4 minutes ago    Exited (0) 6 seconds ago              hungry_lalande
443f3b8cae04   nginx     "/docker-entrypoint.…"   4 minutes ago    Up 4 minutes                80/tcp    wonderful_ramanujan
```
