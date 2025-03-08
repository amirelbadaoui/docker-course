# Docker Learning Repository 🚀

This repository serves as a documentation hub for my journey into **Docker**. I'm following the [Learn Docker in 1 Hour](https://www.youtube.com/watch?v=GFgJkfScVNU&ab_channel=JavaScriptMastery) course by JavaScript Mastery. The goal is to understand Docker fundamentals, containerization, and practical applications.

## 📌 Topics Covered
1. **Introduction to Docker**
2. **Installing Docker**
3. **Docker Images & Containers**
4. **Docker Commands (run, build, exec, logs, etc.)**
5. **Dockerfile Basics**
6. **Docker Compose**
7. **Networking & Volumes**
8. **Building & Running Custom Containers**
9. **Pushing Images to Docker Hub**
10. **Final Project & Real-World Applications**

## 🛠️ Useful Docker Commands
```sh
# Check Docker version
docker --version

# List running containers
docker ps

# Stop a container
docker stop <container_id>

# Remove a container
docker rm <container_id>

# Build an image from a Dockerfile
docker build -t myapp .

# Run a container from an image
docker run -d -p 3000:3000 myapp

# View logs of a running container
docker logs <container_id>