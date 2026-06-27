# 🚀 HireSense AI - Production-Ready AI Interview Preparation Platform

HireSense AI is a production-ready full-stack web application that helps job seekers prepare for interviews using **Generative AI**. The platform analyzes resumes and job descriptions to generate personalized interview reports, identify skill gaps, create preparation roadmaps, and generate ATS-optimized resumes.

The application is containerized with Docker, deployed on Kubernetes, and follows a complete **GitOps CI/CD** workflow using GitHub Actions and ArgoCD.

---

# ✨ Features

* 📄 Upload resume (PDF)
* 🤖 AI-powered interview report generation using Google Gemini
* 🎯 Job description analysis
* 📊 Resume-job match score
* 💡 Technical interview questions with detailed answers
* 🗣️ Behavioral interview questions
* 📈 Skill gap analysis
* 📅 Personalized interview preparation roadmap
* 📑 AI-generated ATS-friendly resume
* 🔐 Secure JWT Authentication
* ☁️ Production-ready Kubernetes deployment
* 📊 Real-time monitoring with Prometheus & Grafana

---

# 🧠 AI Capabilities

HireSense AI leverages **Google Gemini AI** to provide personalized interview preparation by:

* Parsing uploaded resumes
* Understanding job descriptions
* Performing resume-to-job matching
* Generating technical interview questions
* Generating behavioral interview questions
* Identifying missing skills
* Creating structured preparation plans
* Generating ATS-optimized resumes
* Returning structured JSON responses using Zod schema validation

---

# 🏗️ Architecture

```
                 User
                   │
                   ▼
          React Frontend
                   │
          NGINX Ingress Controller
                   │
                   ▼
          Node.js + Express Backend
                   │
      -----------------------------
      │                           │
      ▼                           ▼
 MongoDB Atlas             Google Gemini AI
```

---

# ⚙️ Tech Stack

## Frontend

* React.js
* Vite
* Tailwind CSS
* Axios

## Backend

* Node.js
* Express.js
* MongoDB
* JWT Authentication
* Multer
* PDF-Parse
* Puppeteer

## AI & GenAI

* Google Gemini AI
* Prompt Engineering
* LLM Integration
* Structured JSON Output
* Zod Schema Validation

## DevOps

* Docker
* Kubernetes (Kind)
* NGINX Ingress Controller
* Horizontal Pod Autoscaler (HPA)
* GitHub Actions
* ArgoCD
* GitOps
* Docker Hub

## Monitoring

* Prometheus
* Grafana

---

# 📂 Project Structure

```
HireSense-AI/

├── Frontend/
├── Backend/
├── k8s/
│   └── manifests/
├── .github/
│   └── workflows/
├── README.md
```

---

# 🚀 CI/CD Pipeline

The project implements a complete GitOps workflow.

```
Developer Push
        │
        ▼
GitHub Repository
        │
        ▼
GitHub Actions
        │
        ├── Build Backend Image
        ├── Build Frontend Image
        ├── Push Images to Docker Hub
        └── Update Kubernetes Manifests
                     │
                     ▼
             Commit Changes to Git
                     │
                     ▼
                ArgoCD Detects Change
                     │
                     ▼
              Kubernetes Sync
                     │
                     ▼
             Rolling Deployment
```

---

# ☸️ Kubernetes Features

* Multi-Pod Deployment
* ReplicaSets
* Kubernetes Services
* NGINX Ingress Controller
* Horizontal Pod Autoscaler
* Readiness Probes
* Liveness Probes
* Kubernetes Secrets
* Resource Requests & Limits

---

# 📊 Monitoring & Observability

Integrated monitoring using **Prometheus** and **Grafana**.

Monitored metrics include:

* Pod Health
* CPU Utilization
* Memory Utilization
* Kubernetes Resource Usage
* Deployment Health
* Cluster Metrics

---

# 🔐 Authentication

* JWT Authentication
* Protected API Routes
* Password Hashing
* Secure Cookie-based Authentication

---

# 📦 Deployment

The application is fully containerized using Docker and deployed on a Kubernetes (Kind) cluster.

Deployment includes:

* Docker Images
* Kubernetes Deployments
* Kubernetes Services
* NGINX Ingress
* Horizontal Pod Autoscaler
* Kubernetes Secrets

---

# 🎯 Key Highlights

* Production-ready Full Stack Application
* AI-powered Interview Preparation Platform
* Google Gemini LLM Integration
* ATS Resume Generation
* Kubernetes-based Deployment
* GitOps CI/CD using GitHub Actions & ArgoCD
* Dockerized Microservice-style Architecture
* Production Monitoring with Prometheus & Grafana
* Cloud-native Deployment Practices

---

# 🛠️ Local Setup

## Clone Repository

```bash
git clone https://github.com/<your-username>/HireSense-AI.git

cd HireSense-AI
```

## Backend

```bash
cd Backend

npm install

npm run dev
```

## Frontend

```bash
cd Frontend

npm install

npm run dev
```

---

# 🐳 Docker

Build Backend

```bash
docker build -t backend ./Backend
```

Build Frontend

```bash
docker build -t frontend ./Frontend
```

---

# ☸️ Kubernetes Deployment

```bash
kubectl apply -f k8s/manifests/
```

Verify:

```bash
kubectl get all -n hiresense
```

---

# 📈 Future Improvements

* Multi-LLM Support
* Resume Version History
* AI Mock Interview Voice Assistant
* AI Chat Assistant
* Email Notifications
* Multi-language Support
* AWS EKS Deployment
* Helm Charts
* Terraform-based Infrastructure Provisioning

---

# 👨‍💻 Author

**Gaurav Singh**

* GitHub: https://github.com/singh-gauravv
* LinkedIn: https://www.linkedin.com/in/gauravsinghdevops/
