# 🚀 CI/CD Pipeline with GitHub Actions & Docker

This project demonstrates a **complete CI/CD pipeline** that automatically builds, tests, pushes, and runs a Dockerized application using **GitHub Actions** — no external cloud required.

---

## 🧩 Project Structure

ci-cd-docker-demo/
│
├── app.py # Simple Flask app
├── requirements.txt # Python dependencies
├── Dockerfile # Defines container build
├── docker-compose.yml # Local container orchestration
└── .github/
└── workflows/
└── ci-cd.yml # CI/CD workflow definition

yaml


---

## ⚙️ Prerequisites

Before starting, make sure you have:

- [Docker Desktop](https://www.docker.com/products/docker-desktop) installed  
- [Git](https://git-scm.com/) and [GitHub](https://github.com/) account  
- [Python 3.9+](https://www.python.org/) (optional for local testing)
- A [Docker Hub](https://hub.docker.com/) account

---

## 🧠 Step-by-Step Setup Guide

1️⃣ Create the Project
Create the following files:

app.py
requirements.txt
Dockerfile
docker-compose.yml

2️⃣ Initialize Git Repository

3️⃣ Set Up Docker Hub Secrets
Go to Docker Hub → Account Settings → Security
Click “New Access Token”
Copy the token (you’ll use it once)
Then in GitHub → Your Repository → Settings → Secrets and variables → Actions, add:
Name	Value
DOCKER_USERNAME	your Docker Hub username
DOCKER_PASSWORD	your Docker Hub access token

4️⃣ Create CI/CD Workflow
Path: .github/workflows/ci-cd.yml

5️⃣ Trigger the Workflow
Make a small change to trigger GitHub Actions:

✅ Verification Steps
After workflow completes:

Go to Docker Hub → Repositories
You’ll find ci-cd-demo:latest image uploaded.

Pull and test locally:

bash
docker pull <your-username>/ci-cd-demo:latest
docker run -p 5000:5000 <your-username>/ci-cd-demo:latest
Visit http://localhost:5000
You should see:
“Hello from CI/CD Docker Pipeline!”
