### Run the Docker Compose application with image rebuild
```
$ docker compose up --build
[+] Running 1/1
 ✔ Container simple_service-web-1  Recreated                                                                 0.1s
Attaching to web-1
web-1  | Starting log output
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
web-1  | Wrote text to /usr/src/app/text.log
Gracefully stopping... (press Ctrl+C again to force)
[+] Stopping 1/1
 ✔ Container simple_service-web-1  Stopped                                                                   0.1s

```
