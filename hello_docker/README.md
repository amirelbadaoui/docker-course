# 📦 How to Use Docker | Learning Notes 🚀

This document contains my notes and key takeaways from the [Learn Docker in 1 Hour](https://www.youtube.com/watch?v=GFgJkfScVNU&ab_channel=JavaScriptMastery) video. It serves as a reference for Docker basics.

---

## 📌 Hello Docker Demo
- I create this folder hello_docker
- I then create a js file with a simple console.log statement
- Create a Dockerfile in the folder
- What goes in the Dockerfile?
- First we have to select the base image to run the app
- We want to run a js file so we can use the node runtime from the docker hub
- Typed FROM node:20-alpine into Dockerfile
- We want to send the working directory into /app which is the directory where commands will be run, /app is a standard convention
- Typed WORKDIR /app into Dockerfile
- We will write something to copy everything from our current directory to the docker image
- Typed COPY . .
- The first dot is the current directory on our machine and the second dot is the path to the current directory within the container
- Next we have to specify the command to run the app
- Typed CMD node hello.js
- Move into the folder the Dockerfile is located using terminal
- Type docker build -t hello-docker ("t" stands for tag, its optional)
- You can run the command docker images to see if the image has been created
- Run it === (containerize it) via docker run hello-docker
- If you go into the container and check the files tab, you can see the app folder which contains an exact replica of our host directory
- If you want to open up the application in shell mode, similar to what we did with ubuntu in how_to_use then we have to run docker run -it hello-docker sh

---