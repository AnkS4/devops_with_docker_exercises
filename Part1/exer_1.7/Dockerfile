FROM ubuntu:20.04
WORKDIR /usr/src/app
RUN apt update && apt -y upgrade && apt -y install curl
COPY script.sh .
RUN chmod +x script.sh
CMD ./script.sh

