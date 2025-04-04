## Snake Game in Docker
A simple terminal-based snake game running in a Docker container using Alpine Linux.

### Description
This project containerizes the classic snake game from the bsd-games package using Docker with Alpine Linux as the base image. It provides a lightweight, portable way to enjoy this nostalgic game on any system with Docker installed, without needing to install the game or its dependencies directly on your host machine.

### Technologies
- Docker
- Alpine Linux 3.21
- BSD Games package

### Installation
#### Prerequisites
- Docker installed on your system

### Usage
Run the container with an interactive terminal:

```
# Build from source & run locally built image
docker build . -t alpine-snake && docker run -it alpine-snake

# OR run directly from Docker Hub
docker run -it anks0/alpine-snake
```

#### Game Controls
Use arrow keys to control the snake's direction

Eat the food (represented by symbols) to grow longer

Avoid running into walls or yourself

Press 'q' to quit the game
