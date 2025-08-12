# 🚀 Automated Website Hosting Pipeline

This project demonstrates a fully automated CI/CD pipeline for hosting a static website using **AWS EC2**, **Docker**, **Nginx**, **GitHub Webhooks**, and **Jenkins**.

<img width="1024" height="1536" alt="Create a flowchart d" src="https://github.com/user-attachments/assets/4d7bf220-0592-41b2-ba65-3677ffe569bf" />

## 📦 Tech Stack
- **AWS EC2** – Cloud server for hosting the containerized website
- **Docker** – Containerization of the static HTML/CSS/JS site
- **Nginx** – Web server inside the container to serve static files
- **GitHub Webhooks** – Triggers Jenkins pipeline on code push
- **Jenkins** – Remote CI/CD server for automation

## 🔁 Workflow Overview
1. Developer pushes code to GitHub
2. GitHub webhook triggers Jenkins
3. Jenkins:
   - Clones the repo
   - Builds Docker image
   - Deploys container to EC2
4. Nginx serves the website from the container

## 📂 Project Structure
 ├── Dockerfile ├── index.html ├── styles.css ├── scripts.js └── Jenkinsfil

## 🛠️ Setup Instructions

### 1. Configure EC2
- Launch Ubuntu EC2 instance
- Install Docker and Nginx

### 2. Set Up Jenkins
- Install Jenkins on a remote server
- Configure GitHub webhook
- Create pipeline using `Jenkinsfile`

### 3. Dockerfile Example
 - Remove the files using RUN rm -rf /usr/share/nginx/html/*
 - copy the website using COPY . /usr/share/nginx/htm
 - expose the port 80
 - Run Nginx in background using RUN rm -rf /usr/share/nginx/html/*

### 4. Jenkins file Example.
pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-static-site .'
            }
        }
        stage('Deploy to EC2') {
            steps {
                // Use SSH or Docker context to deploy
            }
        }
    }
}

<br> than the websie looks like this------</br>
<img width="3200" height="1904" alt="image" src="https://github.com/user-attachments/assets/bfa9078e-ffe6-4fa7-81fd-0581f907fd3f" />
<img width="3200" height="1904" alt="image" src="https://github.com/user-attachments/assets/64525e57-5b61-4686-86a1-9d8434283881" />
<img width="3200" height="1904" alt="image" src="https://github.com/user-attachments/assets/101b6da1-23cb-4ba4-b48e-7856b3773495" />
<img width="3200" height="1904" alt="image" src="https://github.com/user-attachments/assets/9ec5a40a-397a-416f-bc60-d9410ebfa86f" />



