# HireSense AI

[![React](https://img.shields.io/badge/React-19.x-blue?logo=react&logoColor=white)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-8.x-brightgreen?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-22.x-green?logo=node.js&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-6.0-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Docker](https://img.shields.io/badge/Docker-Compose-blue?logo=docker&logoColor=white)](https://www.docker.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

A production-oriented full‑stack application that helps candidates prepare for technical interviews by combining resume analysis, job-description parsing, and AI-powered interview plan generation.

This repository contains a React + Vite frontend and a Node.js + Express backend using MongoDB. The application supports user authentication, resume uploads, AI-generated interview reports, and downloadable resume summaries.

## Table of contents
- Project Overview
- Project Highlights
- Skills Demonstrated
- Architecture
- Technical Highlights
- Docker Architecture
- Quick Start
- Development
- Deployment
- API Overview
- Environment variables (.env.example)
- Future Enhancements
- Contributing
- License & Author

## Project Overview

HireSense AI is an end-to-end interview preparation platform that analyzes candidate resumes and job descriptions to produce tailored interview plans and reports. The project demonstrates modern full-stack engineering practices including secure authentication, file upload handling, AI integration, and containerized deployment.

## Project Highlights

- Built a production-ready full-stack AI application with a clear separation of concerns.
- Implemented JWT authentication with protected frontend and backend routes.
- Integrated AI-powered resume and interview analysis workflows.
- Implemented robust file upload handling and PDF resume generation.
- Containerized application with Docker and Docker Compose for reproducible environments.
- Designed a scalable three-tier architecture suitable for cloud deployment.
- Deployed as a containerized multi-service application using Docker and Docker Compose.

## Skills Demonstrated

- React
- Vite
- Node.js
- Express.js
- MongoDB
- REST APIs
- JWT Authentication
- Docker
- Docker Compose
- AI Integration
- File Upload Handling
- Full-Stack Development

## Architecture

Logical flow (browser → frontend → backend → database):

```
┌─────────────┐
│   Browser   │
└──────┬──────┘
│
▼
┌─────────────┐
│ React + Vite│
│  Frontend   │
└──────┬──────┘
│ REST API
▼
┌─────────────┐
│ Node.js API │
│  Express    │
└──────┬──────┘
│
▼
┌─────────────┐
│  MongoDB    │
└─────────────┘
```

Flow summary:

- The browser loads the SPA served by the frontend (static build or Vite dev server).
- The frontend issues REST API requests to the backend for authentication, report creation, and reading reports.
- The backend performs business logic, invokes AI services for analysis, processes uploads, and persists results to MongoDB.

Security notes:

- Avoid exposing MongoDB to the public internet. Use network isolation, authentication, and managed DB services in production.
- Provide secrets via environment variables, Docker secrets, or a secret manager rather than committing them to source control.

## Technical Highlights

- Full-stack architecture with a client-first SPA and RESTful backend.
- JWT authentication with secure handling and protected routes.
- Resume ingestion and parsing pipeline with AI-assisted analysis.
- File upload handling (multipart/form-data) and PDF generation.
- Containerized services for consistent development and demo environments.

## Docker Architecture

Container communication (visual):

```
+-----------+        +----------------------+        +-----------------------+
|  Browser  | <----> | Frontend Container   | <----> | Backend Container    |
+-----------+        +----------------------+        +-----------------------+
|
v
+-----------+
| MongoDB   |
+-----------+
```

- `mongo`: MongoDB service (persistent volume `mongo-data`).
- `backend`: Node.js API server. Connects to MongoDB using `MONGO_URI=mongodb://mongo:27017/hiresense`.
- `frontend`: Static SPA served by a lightweight Node runtime in the production Dockerfile.

Networking and security notes:

- Services run on a user-defined compose network; service names resolve as hostnames (for example `mongo`).
- Do not expose the MongoDB service to the public internet in production; use private networks and appropriate authentication.

## Quick Start

Run the full stack with Docker Compose (recommended):

```bash
git clone https://github.com/singh-gauravv/HireSense-Ai.git
cd "FullStack-HireSense AI"

# Build and start services
docker compose build --no-cache
docker compose up
```

Default endpoints:
- Backend: http://localhost:3000
- Frontend: http://localhost (port 80)

Stop and remove volumes:

```bash
docker compose down -v
```

## Development (local without Docker)

Backend

```bash
cd Backend
npm install
# create Backend/.env per the example below
npm run dev
```

Frontend

```bash
cd Frontend
npm install
npm run dev
# Vite dev server typically runs at http://localhost:5173
```

## Deployment

For production deployment consider:
- Kubernetes with Deployments, Services and Ingress (TLS termination).
- Managed MongoDB (Atlas) or a properly configured replica set.
- CI/CD pipelines for automated builds, tests, and image publishing.
- Use secret management for credentials (Vault, cloud secrets).

Minimal production steps:
1. Build images and push to a container registry.
2. Deploy with your orchestration platform (Kubernetes, ECS, etc.).
3. Configure HTTPS, monitoring, and backups.

## API Overview

### Auth

- `POST /api/auth/register` — Register a user.
- `POST /api/auth/login` — Authenticate and receive a JWT (cookie or header).
- `GET /api/auth/get-me` — Get the authenticated user.

### Interview

- `POST /api/interview` — Create an interview report (multipart/form-data, supports resume upload).
- `GET /api/interview` — List the authenticated user's reports.
- `GET /api/interview/report/:interviewId` — Retrieve a specific report.
- `POST /api/interview/resume/pdf/:interviewReportId` — Generate or download a resume PDF.

Refer to `Backend/src/controllers` for implementation details and request/response formats.

## Environment variables (.env.example)

Create a `Backend/.env` file from the example below. Do not commit secrets to source control.

```env
MONGO_URI=
JWT_SECRET=
GOOGLE_GENAI_API_KEY=
PORT=3000
NODE_ENV=development
```

## Future Enhancements

- OAuth login (Google / GitHub) for streamlined onboarding.
- Kubernetes deployment with Helm charts and autoscaling.
- CI/CD pipeline with automated tests, security scans and image promotion.
- Redis caching for session and frequently accessed data.
- Role-based access control (RBAC) and administration UI.
- AI interview chatbot for conversational practice and feedback.
- ATS resume scoring and standardized exports for recruiter workflows.
- Observability: metrics, tracing and centralized logging (Prometheus, Grafana, ELK).

## Repository Setup Recommendations

Include these files in the repository to improve security, clarity, and contributor experience:

- `LICENSE` — Add an open-source license (MIT recommended) to clarify usage and contribution terms.
- `.gitignore` — Exclude `node_modules`, build artifacts, local environment files, and other temporary files from version control.
- `Backend/.env.example` — Provide a template of required environment variables (keys only) so contributors can run the project locally without exposing secrets.

Providing these files helps maintainers and contributors get started quickly and reduces accidental leaks of sensitive data.

## GitHub Repository Topics

Recommended topics to add on the GitHub repository page for discoverability and categorization:

- react
- vite
- nodejs
- express
- mongodb
- docker
- docker-compose
- jwt-authentication
- fullstack
- ai
- genai
- resume-parser
- interview-preparation

## Contributing

Contributions are welcome. Suggested workflow:
1. Fork the repository and create a descriptive branch: `feature/<name>` or `fix/<issue>`.
2. Run tests and linters locally.
3. Open a Pull Request with a clear summary and any migration steps.
4. Respond to review comments and keep the PR focused and atomic.

Please follow the existing code style and add tests for new functionality when appropriate.

## License & Author

Author: Gaurav Singh



