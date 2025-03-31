### Navigate to the spring example project directory
### Build a Docker image and run it with port mapping
```
$ cd ~/material-applications/spring-example-project/
$ docker build . -t spring-project && docker run -p 8080:8080 spring-project
[+] Building 0.4s (9/9) FINISHED                                                                   docker:default
 => [internal] load build definition from Dockerfile                                                         0.0s
 => => transferring dockerfile: 190B                                                                         0.0s
 => [internal] load metadata for docker.io/library/amazoncorretto:latest                                     0.3s
 => [internal] load .dockerignore                                                                            0.0s
 => => transferring context: 2B                                                                              0.0s
 => [1/4] FROM docker.io/library/amazoncorretto:latest@sha256:33125c389b8242e8539cd6e30ef8514036ba6cf00638a  0.0s
 => [internal] load build context                                                                            0.0s
 => => transferring context: 1.31kB                                                                          0.0s
 => CACHED [2/4] WORKDIR /usr/src/app                                                                        0.0s
 => CACHED [3/4] COPY . .                                                                                    0.0s
 => CACHED [4/4] RUN ./mvnw package                                                                          0.0s
 => exporting to image                                                                                       0.0s
 => => exporting layers                                                                                      0.0s
 => => writing image sha256:4959edcfad5a2ba1dd1e916af26544950752f2a7d3925d5ff2fcc5f6abd1476e                 0.0s
 => => naming to docker.io/library/spring-project                                                            0.0s

 .   ____          _            __ _ _ 
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \ 
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/ 
 :: Spring Boot ::        (v2.1.3.RELEASE)

 2025-03-19 15:19:47.812  INFO 1 --- [           main] c.d.dockerexample.DemoApplication        : Starting DemoApplication v1.1.3 on 73bde6d2caaa with PID 1 (/usr/src/app/target/docker-example-1.1.3.jar started by root in /usr/src/app)
2025-03-19 15:19:47.815  INFO 1 --- [           main] c.d.dockerexample.DemoApplication        : No active profile set, falling back to default profiles: default
2025-03-19 15:19:49.294  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2025-03-19 15:19:49.334  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service
[Tomcat]
2025-03-19 15:19:49.335  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servletengine: [Apache Tomcat/9.0.16]
2025-03-19 15:19:49.349  INFO 1 --- [           main] o.a.catalina.core.AprLifecycleListener   : The APR based Apache Tomcat Native library which allows optimal performance in production environments was not found on the java.library.path: [/usr/java/packages/lib/amd64:/usr/lib64:/lib64:/lib:/usr/lib]
2025-03-19 15:19:49.439  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2025-03-19 15:19:49.439  INFO 1 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1556 ms
2025-03-19 15:19:49.731  INFO 1 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2025-03-19 15:19:49.945  INFO 1 --- [           main] o.s.b.a.w.s.WelcomePageHandlerMapping    : Adding welcome page template: index
2025-03-19 15:19:50.189  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2025-03-19 15:19:50.193  INFO 1 --- [           main] c.d.dockerexample.DemoApplication        : Started DemoApplication in 2.884 seconds (JVM running for 3.445)
2025-03-19 15:20:00.088  INFO 1 --- [nio-8080-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring DispatcherServlet 'dispatcherServlet'
2025-03-19 15:20:00.088  INFO 1 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2025-03-19 15:20:00.097  INFO 1 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 9 ms
```
