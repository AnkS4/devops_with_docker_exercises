### ### Launch a multi-container app with Redis, backend, frontend, and 5 compute instances using Docker Compose

```
$ docker compose up --scale compute=5 -d
[+] Running 8/8
 ✔ Network scaling-exercise_default      Created                                                                                                                                                                                 0.2s 
 ✔ Container scaling-exercise-compute-5  Started                                                                                                                                                                                 0.2s 
 ✔ Container load-balancer               Started                                                                                                                                                                                 0.3s 
 ✔ Container calculator                  Started                                                                                                                                                                                 0.3s 
 ✔ Container scaling-exercise-compute-1  Started                                                                                                                                                                                 0.8s 
 ✔ Container scaling-exercise-compute-2  Started                                                                                                                                                                                 0.6s 
 ✔ Container scaling-exercise-compute-4  Started                                                                                                                                                                                 0.5s 
 ✔ Container scaling-exercise-compute-3  Started
```
