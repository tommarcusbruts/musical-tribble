# 📌 Task: Automate Code Deployment Using CI/CD Pipeline

This repository fulfills **Task 1** of a DevOps internship assignment. The goal was to automate the deployment of a Node.js application using a CI/CD pipeline with GitHub Actions and Docker.

---


## 👋 Author 

Tom Marcus Brut
Building DevOps pipelines, breaking limitations.
## 🎯 Objective
Set up a CI/CD pipeline that:
- Automatically builds and tests a Node.js app
- Creates a Docker image
- Pushes the image to DockerHub
- Deploys the app for live access

---
## 🧰 Tech Stack & Tools

| Tool           | Purpose                         |
|----------------|----------------------------------|
| Node.js        | Backend application              |
| Docker         | Containerization                 |
| GitHub Actions | CI/CD pipeline automation        |
| DockerHub      | Container registry               |
| Render         | Free app hosting (for live demo) |
| Cron-job.org   | Keep app alive workaround        |

---
## Project Setup
This project is based on a simple Node.js app (`index.js`) using Express, which runs on port `3000`.



### 📁 Key Files
```bash
- Dockerfile – Defines how the app is containerized
- .github/workflows/main.yml – GitHub Actions pipeline
- index.js – Node.js Express app
- package.json – Dependencies and scripts

```
## ⚙️ CI/CD Workflow: GitHub Actions
### 📄 `.github/workflows/main.yml`

The GitHub Actions workflow is triggered on every push to the `main` branch and does the following:

1. *Install Dependencies*
2. *Run Dummy Tests*
3. *Build Docker Image*
4. *Push Image to DockerHub*

```yaml
- name: Run Dummy Test
  run: echo "No test cases yet"
  ```
## 📦 DockerHub Image

The Docker image is automatically built and pushed via GitHub Actions.

🔗 DockerHub:
👉 https://hub.docker.com/r/omtusharkant/nodejs-demo-app
## 🌐 Live Deployment on Render

The app is hosted using Render, which builds directly from this GitHub repo.

🔗 Live URL:
👉 https://demo-node-js-ugo6.onrender.com/



## 🛡️ Uptime Workaround for Render

Since Render’s free tier spins down after 15 minutes of inactivity, I configured an external cron job to ping the app every 14 minutes.

🔧 Cron Setup:

    Website: https://console.cron-job.org

    Type: HTTP GET request

    URL: https://demo-node-js-ugo6.onrender.com/

    Interval: Every 14 minutes

✅ This ensures the app stays warm and loads quickly for reviewers
## ✅ Status

✔️ CI/CD pipeline tested  
✔️ Docker image built and pushed  
✔️ Live app hosted on Render  
✔️ Uptime managed using cron-job.org  
✔️ Task 1 successfully completed!
