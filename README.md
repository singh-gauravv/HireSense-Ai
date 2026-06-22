# HireSense AI 🚀

AI-powered Interview Preparation Platform built with **React, Node.js, MongoDB Atlas, Docker, Kubernetes (Kind), NGINX Ingress, HPA, and Gemini AI**.

---

# 📸 Project Screenshots

## Architecture Diagram
![Architecture](screenshots/architecture.png)

## Login Page
![Login](screenshots/login-page.png)

## Dashboard
![Dashboard](screenshots/dashboard.png)

## Kubernetes Node
![Node](screenshots/k8s-node.png)

## Running Pods
![Pods](screenshots/k8s-pods.png)

## Deployments
![Deployments](screenshots/k8s-deployments.png)

## Services
![Services](screenshots/k8s-services.png)

## Ingress
![Ingress](screenshots/k8s-ingress.png)

## Ingress Description
![Ingress Description](screenshots/k8s-ingress-describe.png)

## Horizontal Pod Autoscaler
![HPA](screenshots/k8s-hpa.png)

## Complete Kubernetes Resources
![K8s All](screenshots/k8s-all.png)

## Ingress Port Forward
![Port Forward](screenshots/port-forward.png)

---

# 📌 Overview

HireSense AI helps candidates prepare for interviews by:

- Uploading resumes
- Analyzing job descriptions
- Generating interview strategies
- Detecting skill gaps
- Creating preparation roadmaps
- Generating interview questions
- Producing ATS-friendly resume improvements

---

# 🏗️ Architecture

User Browser
→ NGINX Ingress

NGINX Ingress
├── Frontend Service
└── Backend Service

Backend Service
├── MongoDB Atlas
└── Google Gemini AI

---

# ⚙️ Tech Stack

## Frontend
- React
- Vite
- React Router
- Axios
- SCSS

## Backend
- Node.js
- Express.js
- JWT Authentication
- Multer
- PDF Parse

## Database
- MongoDB Atlas

## AI
- Google Gemini AI

## DevOps
- Docker
- Docker Compose
- Kubernetes (Kind)
- NGINX Ingress Controller
- Horizontal Pod Autoscaler (HPA)

---

# ✨ Features

## Authentication
- User Registration
- User Login
- JWT Authentication
- Protected Routes

## Resume Processing
- PDF Upload
- Resume Parsing
- Profile Extraction

## AI Features
- Interview Strategy Generation
- Technical Questions
- Behavioral Questions
- Skill Gap Analysis
- Match Score Calculation
- Preparation Roadmap

## DevOps Features
- Dockerized Frontend
- Dockerized Backend
- Kubernetes Deployments
- Kubernetes Services
- Ingress Routing
- Horizontal Pod Autoscaling

---

# 🐳 Docker Deployment

## Build Images

```bash
docker build -t singhhgauravv/hiresense-frontend:v1 ./frontend

docker build -t singhhgauravv/hiresense-backend:v1 ./backend
```

## Run Containers

```bash
docker compose up -d
```

---

# ☸️ Kubernetes Deployment

## Create Cluster

```bash
kind create cluster --name hiresense
```

## Deploy Resources

```bash
kubectl apply -f k8s/
```

## Verify

```bash
kubectl get nodes

kubectl get pods -n hiresense

kubectl get deployments -n hiresense

kubectl get svc -n hiresense

kubectl get ingress -n hiresense

kubectl get hpa -n hiresense
```

---

# 🌐 Access Application

Expose ingress controller:

```bash
kubectl port-forward -n ingress-nginx svc/ingress-nginx-controller 8080:80
```

Open:

```text
http://localhost:8080
```

---

# 📂 Kubernetes Resources

- Namespace
- Frontend Deployment
- Backend Deployment
- Frontend Service
- Backend Service
- NGINX Ingress
- Backend HPA
- Frontend HPA
- Kubernetes Secrets

---

# 🔑 Environment Variables

## Backend

```env
PORT=3000

MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

GOOGLE_GENAI_API_KEY=your_gemini_api_key
```

---

# 📡 API Endpoints

## Auth

```http
POST /api/auth/register

POST /api/auth/login

GET /api/auth/get-me

GET /api/auth/logout
```

## Interview

```http
POST /api/interview

GET /api/interview

GET /api/interview/report/:interviewId

POST /api/interview/resume/pdf/:interviewReportId
```

---

# 🏆 Key Learnings

- Docker Containerization
- Kubernetes Deployments
- Services & Networking
- Ingress Controller
- Horizontal Pod Autoscaling
- MongoDB Atlas Integration
- JWT Authentication
- File Upload Handling
- AI Integration using Gemini
- Full Stack Development
- DevOps Best Practices

---

# 🚀 Future Enhancements

- GitHub Actions CI
- ArgoCD GitOps CD
- Helm Charts
- Prometheus Monitoring
- Grafana Dashboards
- Loki Logging
- Trivy Image Scanning
- SonarQube Integration
- AWS EKS Deployment

---

# 👨‍💻 Author

Gaurav Singh

GitHub: https://github.com/singh-gauravv