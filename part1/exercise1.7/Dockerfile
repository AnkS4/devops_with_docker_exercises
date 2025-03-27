# Start from the ubuntu 24.04 image
FROM ubuntu:24.04

# Use /usr/src/app as our workdir. The following instructions will be executed in this location.
WORKDIR /usr/src/app

# Copy the script.sh file from this directory to /usr/src/app/
COPY script.sh .

# Execute apt commands to install curl
RUN apt update -y
RUN apt install curl -y

# When running docker run the command will be ./hello.sh
CMD ./script.sh
