### Create an empty log file in the current directory
### Run the container with a volume mount so that the logs are created into host filesystem
```
$ touch $(pwd)/text.log
$ docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
Starting log output
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
^C
```
