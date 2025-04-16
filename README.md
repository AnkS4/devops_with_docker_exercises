# DevOps with Docker

A repository containing exercise solutions for the DevOps with Docker course offered by the University of Helsinki. The course provides a comprehensive introduction to Docker, containerization, and essential DevOps practices, structured into three progressive parts.

The exercises are designed to reinforce theoretical knowledge through hands-on application, ensuring learners develop proficiency in building, managing, and optimizing containerized applications.


## Repository Structure

The repository is organized into parts and exercises, with each exercise directory containing relevant files such as Dockerfile, commands.md, script.sh. Below is the folder hierarchy:

```
├── part1
│   ├── exercise1.1
│   │   ├── commands.md
│   │   ├── Dockerfile
│   │   └── script.sh
│   │   └── ...
│   ├── exercise1.2
│   │   └── ...
│   └── exercise1.x
│       └── ...
├── part2
│   ├── exercise2.1
│   │   └── ...
│   └── ...
└── ...
```

Each exercise folder contains all the necessary files to complete or understand the particular exercise. These may include:

- `commands.md`: Contains the Docker commands used in the exercise along with the output
- `Dockerfile`: The Dockerfile used to build the image
- `script.sh`: Helper scripts for automating tasks
- Other configuration and source files as needed

## Overview

This repository contains solutions and exercises for learning Docker and DevOps practices. The exercises are organized by parts, with each part focusing on different aspects of Docker and containerization.

### Part 1: Docker Fundamentals

Part 1 introduces essential Docker concepts through hands-on exercises aligned with the [course objectives](https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker/chapter-2). Learners progress from running basic containers to deploying interconnected multi-service applications.

#### Key Learning Objectives
- **Run containerized applications**: Learn how to start, stop, and manage containers using core Docker commands.
- **Containerize applications**: Create custom Docker images using `Dockerfile` to package applications and dependencies.
- **Utilize volumes**: Store data persistently outside containers to ensure data integrity across container restarts.
- **Use port mapping**: Expose containerized applications to external networks via TCP ports for accessibility.
- **Share containers publicly**: Build and publish custom images to Docker Hub for reuse and collaboration.

#### Exercise Highlights
- **Container Lifecycle Management**: Master commands like `docker run`, `stop`, `rm`, `ps`, and `exec` to manage containers effectively (Exercises 1.1–1.4).
- **Image Creation**: Build custom images using `Dockerfile` with best practices for layering and caching (Exercises 1.7–1.8).
- **Persistent Data Storage**: Configure volumes to retain logs and application data beyond container lifetimes (Exercise 1.9).
- **Network Exposure**: Use port mapping (`docker run -p`) to make containerized applications accessible externally (Exercise 1.10).
- **Cross-Container Communication**: Set up interconnected services (e.g., frontend-backend) with proper networking configurations (Exercises 1.12–1.14).
- **Build and Publish Images**: Create your own Docker images and share them publicly via Docker Hub (Exercise 1.15).

### Part 2: Docker Compose & Orchestration Fundamentals  

Part 2 focuses on multi-container application management using Docker Compose, aligned with [course objectives](https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker/chapter-3). Learners progress from basic service definitions to complex orchestration scenarios.

#### Key Learning Objectives  
- **Multi-Service Architecture**: Coordinate interconnected containers (web apps, databases, caching).
- **Docker Compose Syntax**: Master `docker-compose.yml` structure for service definitions.
- **Environment Management**: Configure shared networks, volumes, and environment variables across services.
- **Dependency Handling**: Control startup order with `depends_on` and health checks.
- **Production Patterns**: Implement restart policies and resource constraints.

#### Exercise Highlights
- **Compose Basics**: Define and manage multi-service applications using `docker-compose.yml` (Exercises 2.1–2.3).
- **Service Integration & Persistence**: Integrate Redis and PostgreSQL services with persistent volumes for data durability and explore scaling service instances (Exercises 2.4–2.6).
- **Host-Container Interaction**: Use bind mounts to enable file sharing between the host system and containers (Exercise 2.7).
---

### Part 3

#### Key Learning Objectives
---

#### Exercise Highlights
---

## Getting Started

### 1. Environment Setup
```bash
# Install Docker & Compose following OS specific instructions

# Verify installation
docker --version && docker-compose --version
```

### 2. Repository Setup
```bash
git clone https://github.com/AnkS4/devops_with_docker.git
cd devops_with_docker/part1/exercise1.1
```

### 3. Exercise Workflow
1. Study `commands.md` for exercise objectives
2. Modify `Dockerfile` as needed
3. Execute build/run commands from terminal
4. Verify outputs against exercise requirements


## Recommended Learning Path
1. Review [official course materials](https://devopswithdocker.com)
2. Complete exercises sequentially (1.1 → 1.2 → … → 1.x → 2.1 → 2.2 → … → 3.x)


## Prerequisites

To utilize this repository effectively:

- Install Docker Engine and Docker Compose on your local machine

- Basic familiarity with Linux command-line interfaces

- A text editor (e.g., nano) for modifying Dockerfiles and scripts.


## License

This repository is licensed under the **Creative Commons BY-NC-SA 4.0** license, the same as the original course materials from the University of Helsinki's *DevOps with Docker* course. For more details, see the [LICENSE](LICENSE) file in this repository or [Creative Commons BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

---
