# 📝 Basic CRUD App

A lightweight full-stack CRUD application built with Node.js, HTML, CSS, and JavaScript. No frameworks, no containers — just the core app. This is **Stage 0** of a four-part DevOps series that progressively containerizes, orchestrates, and packages this same application.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Why This Project](#why-this-project)
- [The Four-Stage DevOps Series](#the-four-stage-devops-series)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [API Endpoints](#api-endpoints)
- [CI/CD Pipeline](#cicd-pipeline)
- [Extending This Blueprint](#extending-this-blueprint)
- [Contributing](#contributing)

---

## Overview

This repository is the starting point of a complete DevOps learning series. It's a functional full-stack CRUD application — a clean, minimal codebase that deliberately avoids infrastructure complexity so the app logic is easy to understand before layering on containerization and orchestration in later stages.

It covers:

- A **Node.js REST API** backend with full Create, Read, Update, Delete operations
- A **vanilla JavaScript frontend** (no frameworks) that consumes the API
- A **GitHub Actions workflow** for basic CI automation
- A project structure designed to be easily containerized in the next stage

---

## Why This Project

Every DevOps journey has to start somewhere — and it should start with a working app.

Before you can containerize something, you need to understand what it does. Before you can write a `Dockerfile`, you need to know how the app runs. This project is that foundation.

It's intentionally bare: no Docker, no Kubernetes, no Helm. Just a working Node.js app with a clean separation between `client` and `server`, structured so that each subsequent stage in the series can be applied with minimal friction.

Think of it as the **"raw ingredients"** — the app that gets progressively wrapped in more powerful infrastructure with each stage.

---

## The Four-Stage DevOps Series

This project is **Stage 0** of a four-part series. Each stage takes the same CRUD app further along the DevOps maturity curve:

| Stage | Repository | What It Adds |
|-------|-----------|--------------|
| 📝 **Stage 0** | [`basic-crudapp`](https://github.com/rishabhnama/basic-crudapp) *(this repo)* | Raw Node.js app — the foundation |
| 🐳 **Stage 1** | [`container-crud`](https://github.com/rishabhnama/container-crud) | Dockerize the app + automated CI/CD |
| ☸️ **Stage 2** | [`kubernetes-crud`](https://github.com/rishabhnama/kubernetes-crud) | Deploy to Kubernetes with YAML manifests |
| ⎈ **Stage 3** | [`helmcrud`](https://github.com/rishabhnama/helmcrud) | Package as a Helm chart for repeatable deployments |

Follow the series from top to bottom to see how the same app evolves from a local Node.js process to a fully orchestrated, Helm-managed Kubernetes deployment.

---

## Tech Stack

| Layer      | Technology               |
|------------|--------------------------|
| Frontend   | HTML, CSS, JavaScript    |
| Backend    | Node.js                  |
| CI/CD      | GitHub Actions           |

---

## Project Structure

```
basic-crudapp/
├── .github/
│   └── workflows/         # GitHub Actions CI pipeline
├── client/                # Frontend — HTML, CSS, JavaScript
│   ├── index.html
│   ├── style.css
│   └── app.js
├── server/                # Backend — Node.js REST API
│   ├── index.js           # Entry point
│   ├── routes/            # API route handlers
│   └── db.js              # Database connection
└── README.md
```

---

## Prerequisites

- [Node.js](https://nodejs.org/) v16+
- [npm](https://www.npmjs.com/)
- A running MySQL instance (local or remote)

---

## Getting Started

**1. Clone the repository:**

```bash
git clone https://github.com/rishabhnama/basic-crudapp.git
cd basic-crudapp
```

**2. Install dependencies:**

```bash
cd server
npm install
```

**3. Configure your database connection:**

Update the database credentials in `server/db.js` (or via environment variables):

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=cruddb
```

**4. Start the server:**

```bash
npm start
```

The app will be running at `http://localhost:3000`.

---

## API Endpoints

The backend exposes a RESTful API for CRUD operations:

| Method   | Endpoint         | Description           |
|----------|------------------|-----------------------|
| `GET`    | `/api/items`     | Fetch all items       |
| `GET`    | `/api/items/:id` | Fetch a single item   |
| `POST`   | `/api/items`     | Create a new item     |
| `PUT`    | `/api/items/:id` | Update an existing item |
| `DELETE` | `/api/items/:id` | Delete an item        |

---

## CI/CD Pipeline

The `.github/workflows/` directory contains a GitHub Actions pipeline that runs on every push to `main`. At this stage it handles basic CI tasks such as dependency installation and linting, keeping the codebase clean before it gets containerized in Stage 1.

---

## Extending This Blueprint

This app is designed to be a starting point. Here's what comes next — both within this series and beyond:

| Enhancement | How |
|---|---|
| **Containerize it** | See [container-crud](https://github.com/rishabhnama/container-crud) — Stage 1 |
| **Deploy to Kubernetes** | See [kubernetes-crud](https://github.com/rishabhnama/kubernetes-crud) — Stage 2 |
| **Package with Helm** | See [helmcrud](https://github.com/rishabhnama/helmcrud) — Stage 3 |
| **Add authentication** | Integrate JWT-based auth with `jsonwebtoken` |
| **Add input validation** | Use `express-validator` or `joi` for request validation |
| **Swap the database** | Replace MySQL with PostgreSQL or MongoDB |
| **Add a frontend framework** | Migrate the vanilla JS frontend to React or Vue |

---

## Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

> 📝 Stage 0 of 4 — [Container](https://github.com/rishabhnama/container-crud) → [Kubernetes](https://github.com/rishabhnama/kubernetes-crud) → [Helm](https://github.com/rishabhnama/helmcrud)
