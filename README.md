# CI/CD Pipeline with GitHub Actions + Docker

This repository demonstrates how to build a **CI/CD pipeline using GitHub Actions and Docker** that automatically builds a Docker image and pushes it to **Docker Hub** whenever code is pushed to the `main` branch.

---

## 📌 Project Overview

**What this project does:**

* Uses GitHub Actions as the CI/CD engine
* Builds a Docker image from application source code
* Pushes the image automatically to a container registry

---

## 🛠 Tech Stack

* Git & GitHub
* GitHub Actions
* Docker
* Docker Hub 
* Python (Flask)

---

## 📂 Project Structure

```
cicd-github-actions-docker/
├── app.py
├── requirements.txt
├── Dockerfile
├── .github/
│   └── workflows/
│       └── docker-build.yml
└── README.md
```

---

## 🚀 CI/CD Workflow Explanation

### Trigger

The pipeline runs automatically on:

```
git push origin main
```

### Workflow Steps

1. Checkout source code
2. Login to Docker Hub (securely using GitHub Secrets)
3. Build Docker image
4. Push image to Docker Hub / ECR

---

## 🔄 Pipeline Diagram

```
Developer
   |
   | git push
   v
GitHub Repository
   |
   v
GitHub Actions Runner
   |
   | docker build
   | docker push
   v
Docker Hub / AWS ECR
```

---

## 🔐 GitHub Secrets Configuration

Add the following secrets in:

**Repository → Settings → Secrets and variables → Actions**

### Docker Hub

| Secret Name     | Description             |
| --------------- | ----------------------- |
| DOCKER_USERNAME | Docker Hub username     |
| DOCKER_PASSWORD | Docker Hub access token |


---

## 🧪 Run Locally (Optional)

```bash
docker build -t cicd-demo .
docker run -d -p 5000:5000 cicd-demo
```

Open:

```
http://localhost:5000
```

---

## 📦 Docker Image

After successful pipeline execution, the image will be available at:

```
docker.io/<docker-username>/cicd-demo:latest
```

---

## 👤 Author

Created as a hands-on DevOps learning project.

---

⭐ If you find this project helpful, consider starring the repository!
