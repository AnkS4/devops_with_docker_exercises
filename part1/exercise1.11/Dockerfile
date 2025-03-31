# Use the latest Amazon Corretto Java image as the base
FROM amazoncorretto:latest

# Expose port 8080 for the application
EXPOSE 8080

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy all files from the current directory to the working directory
COPY . .

# Build the application using Maven wrapper
RUN ./mvnw package

# Command to run the Java application when the container starts
CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
