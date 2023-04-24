FROM openjdk:8
EXPOSE 8080
WORKDIR /usr/src/app

# COPY . .
RUN git clone https://github.com/docker-hy/material-applications.git

# /bin/sh: 1: material-applications/spring-example-project/.: Permission denied
# RUN mv -v material-applications/spring-example-project/* . &&  material-applications/spring-example-project/.* .
RUN mv material-applications/spring-example-project/* .
RUN mv material-applications/spring-example-project/.mvn .

# RUN ls -a material-applications/spring-example-project/
# RUN rm material-applications/spring-example-project/.gitignore
# COPY failed: file not found in build context or excluded by .dockerignore: stat material-applications/spring-example-project: file does not exist
# COPY material-applications/spring-example-project /usr/src/app

# ./mvnw: 216: cannot open /usr/src/app/.mvn/wrapper/maven-wrapper.properties: No such file
# /usr/src/app/.mvn/wrapper/maven-wrapper.jar: No such file or directory
# Error: Could not find or load main class org.apache.maven.wrapper.MavenWrapperMain
# RUN cp -rvp material-applications/spring-example-project/* .

# RUN apt-get update && apt-get install -y rsync
# RUN rsync -av --include="mvn/" material-applications/spring-example-project/* .

# RUN ls -a

RUN ./mvnw package
CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
