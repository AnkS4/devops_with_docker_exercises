FROM golang:1.16
WORKDIR /usr/src/app
EXPOSE 8080
RUN git clone https://github.com/docker-hy/material-applications
RUN mv material-applications/example-backend/* .
RUN go build
CMD ["./server"]
