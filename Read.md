# CRUD MEAN Application (Angular + Node.js + MongoDB)

This repository contains a full-stack CRUD application built with:

Frontend: Angular

Backend: Node.js + Express

Database: MongoDB

Deployment: Docker & Docker Compose

CI/CD: Jenkins Pipeline

This project demonstrates a fully containerized MEAN stack with automated CI/CD deployment.

.

# Features
✔ Angular Frontend

Add / Update / Delete employees

Responsive UI

Uses Bootstrap 4

✔ Node.js Backend

REST API

Mongoose ODM

CRUD routes

Input validation

✔ MongoDB

Stores all employee records

Uses a persistent Docker volume

✔ Docker & CI/CD

Dockerfile for frontend & backend

docker-compose for local development

Jenkins pipeline for complete CI/CD

Pushes images to Docker Hub

Auto-deploys to EC2

# Project Structure

crud-dd-task-mean-app/
│── backend/
│   ├── Dockerfile
│   ├── package.json
│   ├── server.js
│   ├── src/
│
│── frontend/
│   ├── Dockerfile
│   ├── package.json
│   ├── angular.json
│   ├── src/
│
└── Jenkinsfile

# Technologies Used
Layer	Technology
Frontend	Angular 15, TypeScript, Bootstrap
Backend	Node.js, Express.js
Database	MongoDB + Mongoose
Containerization	Docker, Docker Compose
CI/CD	Jenkins Pipeline
Hosting	AWS EC2

# Docker Images And Containers 
<img width="1660" height="418" alt="image" src="https://github.com/user-attachments/assets/4fcb9ff2-665e-4f2e-93e4-590dce25f69b" />

# Docker Setup
Build Backend Image
cd backend
docker build -t your-dockerhub/crud-backend:latest .
<img width="1882" height="550" alt="image" src="https://github.com/user-attachments/assets/a430e08d-416c-4ae9-81b6-830085cf55b6" />


# Build Frontend Image
cd frontend
docker build -t your-dockerhub/crud-frontend:latest .
<img width="1896" height="618" alt="image" src="https://github.com/user-attachments/assets/e711d04c-a37e-4363-9ea5-b7fafe233de2" />

<img width="1913" height="476" alt="image" src="https://github.com/user-attachments/assets/1416ea61-1b0e-4cd4-8b42-f59e76b21389" />

# Run with Docker Compose
docker-compose up -d


# App will be available at:
Frontend → http://localhost
Backend → http://localhost:3000

# CI/CD Pipeline (Jenkins)

This project includes a Jenkinsfile that automates:

✔ Git checkout
✔ Build frontend & backend Docker images
✔ Push to DockerHub
✔ SSH to EC2
✔ Stop running containers
✔ Deploy new images

# Pipeline Stages
 Checkout Code
 Build Docker Images
 Login to DockerHub
 Push to DockerHub
 Deploy to EC2

# Required Credentials
  ID	Type	Purpose
  dockerhub_creds	Username + Password	Push images
  ec2_ssh_key	SSH Key	Deploy to EC2 
  Enable Webhook (GitHub → Jenkins)
  GitHub → Repo → Settings → Webhooks → Add Webhook

# Payload URL:
 http://<JENKINS_URL>/github-webhook/

 
