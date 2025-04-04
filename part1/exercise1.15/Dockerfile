# Use Alpine Linux 3.21 as the base image
FROM alpine:3.21

# Set the working directory inside the container
WORKDIR /usr/src/app

# Update and upgrade the package index
RUN apk update && apk upgrade

# Install the bsd-games package which includes the snake game
RUN apk add bsd-games

# Set the entry point to run the snake game when the container starts
ENTRYPOINT ["snake"]
