# HireSense AI

A professional full-stack application for AI-powered interview preparation.

HireSense AI empowers candidates to generate tailored interview strategies using job descriptions, resume insights, and personal experience. The platform includes secure authentication, resume upload functionality, AI-driven interview reports, and downloadable resume summaries.

## Technology Stack

- **Backend**: Node.js, Express, MongoDB
- **Frontend**: React, Vite, React Router
- **Authentication**: JWT + secure cookie storage
- **AI Integration**: Resume parsing and interview plan generation

## Repository Structure

```text
Backend/
  ├─ package.json
  ├─ server.js
  ├─ src/
  │   ├─ app.js
  │   ├─ config/
  │   │   └─ database.js
  │   ├─ controllers/
  │   │   ├─ auth.controller.js
  │   │   └─ interview.controller.js
  │   ├─ middlewares/
  │   │   ├─ auth.middleware.js
  │   │   └─ file.middleware.js
  │   ├─ models/
  │   │   ├─ blacklist.model.js
  │   │   ├─ interviewReport.model.js
  │   │   └─ user.model.js
  │   ├─ routes/
  │   │   ├─ auth.routes.js
  │   │   └─ interview.routes.js
  │   └─ services/
  │       └─ ai.service.js

Frontend/
  ├─ package.json
  ├─ README.md
  ├─ vite.config.js
  ├─ public/
  └─ src/
      ├─ App.jsx
      ├─ app.routes.jsx
      ├─ main.jsx
      ├─ style.scss
      └─ features/
          ├─ auth/
          └─ interview/
```

## Core Features

- User registration, authentication, and session management
- Secure cookie-based JWT authentication
- Resume upload and AI-assisted interview report generation
- Interview plan dashboard with recent reports
- Downloadable resume PDF export
- Protected UI routes for authenticated users

## Prerequisites

- Node.js 18+
- npm 10+
- MongoDB instance

## Setup Instructions

### 1. Clone the repository

```bash
git clone <repo-url>
cd "FullStack-HireSense AI"
```

### 2. Backend installation

```bash
cd Backend
npm install
```

Create a `.env` file inside the `Backend` folder with the following values:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

### 3. Frontend installation

```bash
cd ../Frontend
npm install
```

## Running the Application

### Backend

```bash
cd Backend
npm run dev
```

Default backend URL: `http://localhost:3000`

### Frontend

```bash
cd ../Frontend
npm run dev
```

Default frontend URL: `http://localhost:5173`

## API Reference

### Authentication

- `POST /api/auth/register` — Register a new user
- `POST /api/auth/login` — Authenticate and create a session
- `GET /api/auth/logout` — End the session and clear auth cookies
- `GET /api/auth/get-me` — Retrieve the current authenticated user

### Interview Report

- `POST /api/interview/` — Create a new interview report (supports file upload)
- `GET /api/interview/` — Get all interview reports for the authenticated user
- `GET /api/interview/report/:interviewId` — Fetch a single interview report
- `POST /api/interview/resume/pdf/:interviewReportId` — Download a generated resume PDF

## Frontend Routes

- `/login` — Login page
- `/register` — Registration page
- `/` — Home page for generating interview plans
- `/interview/:interviewId` — Interview report detail page

## Notes

- The backend allows CORS requests from `http://localhost:5173`.
- The frontend uses `axios` with credentials enabled to support cookie-based authentication.
- Ensure MongoDB is running and the `MONGO_URI` value is set correctly before starting the backend.

## Dependencies

### Backend

- `express`
- `mongoose`
- `bcryptjs`
- `jsonwebtoken`
- `cors`
- `cookie-parser`
- `multer`
- `pdf-parse`
- `puppeteer`
- `dotenv`
- `@google/genai`
- `zod`
- `zod-to-json-schema`

### Frontend

- `react`
- `react-dom`
- `react-router`
- `axios`
- `sass`
- `vite`
- `eslint`

## Author

Gaurav Singh


## Acknowledgements

Built using React, Node.js, MongoDB, Express, and Gemini AI.
