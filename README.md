# Docker Test App

A simple and production-ready **Dockerized application** project that demonstrates how to build, run, and deploy an app using Docker.

---

## 🚀 Project Overview

This project contains a sample application packaged with Docker so it can run consistently across environments. It includes:

* Dockerfile for building the image
* Instructions to run the app in a container
* Commands for pushing/pulling from Docker Hub
* Best practices for Docker development

---

## 📁 Project Structure

```
docker-test-app/
│
├── Dockerfile
├── app/               # Source code folder
│   └── index.js       # Example file (replace with your actual code)
├── package.json       # If Node app (modify based on your tech stack)
└── README.md

## 🔧 How to Build the Docker Image

Run this command inside the project directory:

```bash
docker build -t docker-test-app .
This creates a Docker image named **docker-test-app**.
## ▶️ Run the Application in Docker

Start the container using:

```bash
docker run -p 3000:3000 docker-test-app

## 📤 Push Image to Docker Hub

Login:

```bash
docker login
Tag your image:
docker tag docker-test-app username/docker-test-app:v1
docker push username/docker-test-app:v1
Replace **username** with your Docker Hub ID.

## 📥 Pull Image from Docker Hub

```bash
docker pull username/docker-test-app:v1
docker run -p 3000:3000 username/docker-test-app:v1

## 🛠️ Dockerfile Example

```
# Use Node official image
FROM node:18

# Create app directory
WORKDIR /app

# Copy files
COPY package*.json ./
RUN npm install
COPY . .

# Expose port
EXPOSE 3000

# Start app
CMD ["npm", "start"]

## 📘 Common Docker Commands

| Purpose          | Command              |
| ---------------- | -------------------- |
| List images      | `docker images`      |
| List containers  | `docker ps -a`       |
| Stop container   | `docker stop <id>`   |
| Remove container | `docker rm <id>`     |
| Remove image     | `docker rmi <image>` |
