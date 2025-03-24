### Start a Ubuntu container with a script that prompts for websites and curls them
```
$ docker run -it ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'
Input website:
helsinki.fi
Searching..
sh: 1: curl: not found
Input website:
```

### In the other tab
### List all running Docker containers
```
$ docker ps
CONTAINER ID   IMAGE                                      COMMAND                  CREATED              STATUS            PORTS       NAMES
041db09c3b68   ubuntu                                     "sh -c 'while true; …"   About a minute ago   Up About a minute             condescending_ellis
```

### Connect to the running container with an interactive bash session
### Update package lists and install curl
```
$ docker exec -it condescending_ellis bash
root@041db09c3b68:/# apt update -y && apt install curl -y
Get:1 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble InRelease [256 kB]
...
done.
root@041db09c3b68:/#
```

### Check back in the first tab
### Output after installing curl and entering helsinki.fi in the first terminal
```
Input website:
helsinki.fi
Searching..
<html>
<head><title>301 Moved Permanently</title></head>
<body>
<center><h1>301 Moved Permanently</h1></center>
<hr><center>nginx/1.24.0</center>
</body>
</html>
```
