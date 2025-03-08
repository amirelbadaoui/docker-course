# 📦 How to Use Docker | Learning Notes 🚀

This document contains my notes and key takeaways from the [Learn Docker in 1 Hour](https://www.youtube.com/watch?v=GFgJkfScVNU&ab_channel=JavaScriptMastery) video. It serves as a reference for Docker basics.

---

## 📌 1. Introduction to Docker
- Docker is a tool for **containerizing applications**.
- Containers allow you to run applications in isolated environments.
- Unlike VMs, containers share the host OS kernel, making them **lightweight and fast**.

## 📌 2. Using Docker Commands in Practice (Example)
- We will try to run one of the images in Docker Hub
- Choose one of the OS system images as an example: Ubuntu
- Create a folder for this and drag & drop into VSCode
- Open up your empty terminal and copy and paste the command "docker pull ubuntu"
- Docker initially checks if there are any images with that name on our machine. If not, it goes to Docker Hub and finds the image then automatically installs it on our machine
- Under images, you will see the "ubuntu" image
- We can run a command that executes the image; that process is called "creating a container"
- Run "docker run -it ubuntu" ("it" stands for interactive)
- Reference for next actions -> (18:30)

---