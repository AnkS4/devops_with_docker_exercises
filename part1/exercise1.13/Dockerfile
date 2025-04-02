# Use the official Golang image as the base image
FROM golang:1.24

# Set environment variables for application configuration
# PORT defines the port the server will listen on
# ENV PORT=8080
# REQUEST_ORIGIN defines the allowed origin for CORS requests
ENV REQUEST_ORIGIN=https://example.com

# Expose the port the application will run on
EXPOSE 8080

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy all files from the current directory to the working directory
COPY . .

# Build the Go application
RUN go build

# Command to run when the container starts
CMD ["./server"]
