# 🚀 OpenDesk

### Open-Source Project & Issue Management Platform

OpenDesk is a modern, open-source project management and issue tracking platform built using the **MERN stack**.

It helps individuals and development teams create projects, manage tasks, track bugs, collaborate with team members, and monitor project progress through an intuitive Kanban-based workflow.

The project is designed to demonstrate how a real-world SaaS application can be built using **MongoDB, Express.js, React.js, and Node.js**.

---

## ✨ Features

### 🔐 Authentication & Security

* User registration and login
* JWT-based authentication
* Secure password hashing
* Refresh token support
* Forgot password
* Password reset
* Protected routes
* Role-based authorization
* Session management

---

## 🏢 Organizations

Users can create and manage organizations.

### Organization features

* Create organization
* Update organization details
* Invite team members
* Remove members
* Manage member roles
* Organization settings
* Organization activity logs

### Roles

| Role      | Permissions                     |
| --------- | ------------------------------- |
| Owner     | Full organization access        |
| Admin     | Manage users and projects       |
| Developer | Manage assigned projects/issues |
| Viewer    | Read-only access                |

---

# 📁 Projects

Organizations can contain multiple projects.

Each project can have:

* Project name
* Description
* Project key
* Members
* Status
* Start date
* Target date
* Project manager
* Labels
* Issues

### Example

```text
OpenDesk Organization

├── Website Redesign
│   ├── 23 Issues
│   ├── 5 Members
│   └── 72% Complete
│
├── Mobile Application
│   ├── 41 Issues
│   ├── 7 Members
│   └── 45% Complete
│
└── API Platform
    ├── 18 Issues
    ├── 4 Members
    └── 83% Complete
```

---

# 🐛 Issue Management

Issues are the core of OpenDesk.

Users can create different types of issues.

### Issue Types

* 🐛 Bug
* ✨ Feature
* 📝 Task
* 🔧 Improvement
* 📚 Documentation

### Issue information

Each issue can contain:

```text
Title
Description
Issue Type
Priority
Status
Assignee
Reporter
Labels
Due Date
Attachments
Comments
Activity History
Created Date
Updated Date
```

---

# 📊 Issue Priorities

OpenDesk supports multiple priority levels.

```text
LOW
MEDIUM
HIGH
URGENT
```

Example:

```text
🐛 Login button not working

Priority: HIGH
Type: BUG
Assignee: Abhishek
Status: IN PROGRESS
```

---

# 📋 Kanban Board

OpenDesk provides a drag-and-drop Kanban board.

```text
┌──────────────┐
│   BACKLOG    │
├──────────────┤
│ Issue #101   │
│ Issue #104   │
│ Issue #108   │
└──────────────┘

┌──────────────┐
│     TODO     │
├──────────────┤
│ Issue #102   │
│ Issue #105   │
└──────────────┘

┌──────────────┐
│ IN PROGRESS  │
├──────────────┤
│ Issue #103   │
│ Issue #106   │
└──────────────┘

┌──────────────┐
│    REVIEW    │
├──────────────┤
│ Issue #107   │
└──────────────┘

┌──────────────┐
│     DONE     │
├──────────────┤
│ Issue #99    │
│ Issue #100   │
└──────────────┘
```

Issues can be moved between columns using drag and drop.

---

# 💬 Collaboration

Team members can collaborate directly inside issues.

### Comments

Users can:

* Add comments
* Edit comments
* Delete comments
* Mention team members
* Reply to discussions

Example:

```text
Abhishek

The login API is returning a 401 response
when the refresh token expires.

2 hours ago


Priya

I'll check the authentication middleware.

1 hour ago
```

---

# ⚡ Real-Time Updates

OpenDesk uses **Socket.IO** for real-time communication.

Real-time events include:

* New comments
* Issue assignment
* Issue status changes
* Notifications
* Member invitations
* Activity updates

Example:

```text
Developer A
     │
     │ Changes issue status
     ▼
Node.js + Socket.IO
     │
     ├──────────────► Developer B
     │
     ├──────────────► Project Manager
     │
     └──────────────► Admin
```

---

# 🔔 Notification System

Users receive notifications for important events.

Examples:

```text
🔔 You were assigned Issue #104

🔔 Priya commented on Issue #101

🔔 Issue #103 changed to "Review"

🔔 You were invited to Website Redesign

🔔 Project deadline is approaching
```

---

# 📈 Dashboard

The dashboard provides an overview of project activity.

### Metrics

```text
Projects             12

Open Issues           47

Completed Issues      128

Bugs                  16

Team Members          24

Completion            78%
```

### Analytics

The dashboard can display:

* Issues by status
* Issues by priority
* Issues by type
* Team workload
* Project completion
* Issues created over time
* Issues completed over time

---

# 🔎 Search & Filtering

Users can search and filter issues.

### Search

```text
Search: authentication
```

### Filters

```text
Status
Priority
Assignee
Issue Type
Label
Created Date
Due Date
```

Example:

```text
Status: IN PROGRESS
Priority: HIGH
Assignee: Abhishek
Type: BUG
```

---

# 📎 File Attachments

Users can attach files to issues.

Supported examples:

```text
Images
PDF files
Screenshots
Documents
Logs
```

Files can be stored using services such as:

* Cloudinary
* AWS S3
* Cloudflare R2

---

# 📝 Markdown Support

Issue descriptions and comments can support Markdown.

Example:

```markdown
## Problem

The authentication API returns a 401 error.

### Steps to reproduce

1. Login
2. Wait for token expiration
3. Refresh page

### Expected result

User should remain authenticated.
```

---

# 🧑‍💻 Tech Stack

## Frontend

* React.js
* TypeScript
* Vite
* Tailwind CSS
* React Router
* TanStack Query
* Axios
* Socket.IO Client

## Backend

* Node.js
* Express.js
* TypeScript
* Mongoose
* JWT
* Socket.IO
* Zod
* Multer

## Database

* MongoDB
* MongoDB Atlas

## DevOps

* Docker
* GitHub Actions
* Render / Railway / AWS

---

# 🏗️ Architecture

```text
                     ┌──────────────────┐
                     │      USER        │
                     └────────┬─────────┘
                              │
                              ▼
                     ┌──────────────────┐
                     │   React Client   │
                     │   TypeScript     │
                     └────────┬─────────┘
                              │
                     HTTP / WebSocket
                              │
                              ▼
                  ┌───────────────────────┐
                  │     Express API       │
                  │       Node.js         │
                  └───────────┬───────────┘
                              │
             ┌────────────────┼────────────────┐
             │                │                │
             ▼                ▼                ▼
        Authentication    Issue API       Project API
             │                │                │
             └────────────────┼────────────────┘
                              │
                              ▼
                     ┌──────────────────┐
                     │     Mongoose     │
                     └────────┬─────────┘
                              │
                              ▼
                     ┌──────────────────┐
                     │     MongoDB      │
                     └──────────────────┘
```

---

# 📂 Project Structure

```text
opendesk/
│
├── client/
│   │
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── layouts/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── contexts/
│   │   ├── types/
│   │   ├── utils/
│   │   └── App.tsx
│   │
│   └── package.json
│
├── server/
│   │
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── sockets/
│   │   ├── utils/
│   │   └── server.ts
│   │
│   └── package.json
│
├── docs/
│
├── .env.example
├── .gitignore
├── docker-compose.yml
├── LICENSE
└── README.md
```

---

# 🗄️ Database Models

The initial database design contains the following collections:

```text
User
 │
 ├── Organization
 │       │
 │       ├── Project
 │       │      │
 │       │      └── Issue
 │       │             │
 │       │             ├── Comment
 │       │             ├── Attachment
 │       │             └── Activity
 │       │
 │       └── Members
 │
 └── Notifications
```

### Main models

```text
User
Organization
OrganizationMember
Project
Issue
Comment
Label
Attachment
Notification
ActivityLog
```

---

# 🔌 REST API

Example API structure:

## Authentication

```http
POST /api/auth/register
POST /api/auth/login
POST /api/auth/logout
POST /api/auth/refresh
POST /api/auth/forgot-password
POST /api/auth/reset-password
```

## Users

```http
GET    /api/users
GET    /api/users/:id
PATCH  /api/users/:id
DELETE /api/users/:id
```

## Organizations

```http
POST   /api/organizations
GET    /api/organizations
GET    /api/organizations/:id
PATCH  /api/organizations/:id
DELETE /api/organizations/:id
```

## Projects

```http
POST   /api/projects
GET    /api/projects
GET    /api/projects/:id
PATCH  /api/projects/:id
DELETE /api/projects/:id
```

## Issues

```http
POST   /api/issues
GET    /api/issues
GET    /api/issues/:id
PATCH  /api/issues/:id
DELETE /api/issues/:id
```

## Comments

```http
POST   /api/issues/:issueId/comments
GET    /api/issues/:issueId/comments
PATCH  /api/comments/:id
DELETE /api/comments/:id
```

---

# ⚙️ Installation

## Prerequisites

Make sure the following are installed:

* Node.js
* npm
* Git
* MongoDB or MongoDB Atlas

Check your versions:

```bash
node -v
npm -v
git --version
```

---

# 📥 Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/opendesk.git

cd opendesk
```

---

# 📦 Install Backend

```bash
cd server

npm install
```

---

# 📦 Install Frontend

Open another terminal:

```bash
cd client

npm install
```

---

# 🔐 Environment Variables

Create:

```text
server/.env
```

Example:

```env
PORT=5000

MONGO_URI=mongodb://127.0.0.1:27017/opendesk

JWT_SECRET=your_super_secret_key

JWT_REFRESH_SECRET=your_refresh_secret

CLIENT_URL=http://localhost:5173
```

---

# ▶️ Run Backend

```bash
cd server

npm run dev
```

Backend will run on:

```text
http://localhost:5000
```

---

# ▶️ Run Frontend

```bash
cd client

npm run dev
```

Frontend will run on:

```text
http://localhost:5173
```

---

# 🧪 Testing

The project will include:

### Backend

* Unit tests
* Controller tests
* API integration tests
* Authentication tests

### Frontend

* Component tests
* Page tests
* Form validation tests

Testing tools:

```text
Jest
Supertest
React Testing Library
```

---

# 🐳 Docker

OpenDesk can also be run using Docker.

```bash
docker compose up --build
```

Stop containers:

```bash
docker compose down
```

---

# 🚀 Deployment

The application can be deployed using:

### Frontend

* Vercel
* Netlify

### Backend

* Render
* Railway
* AWS

### Database

* MongoDB Atlas

---

# 🛣️ Roadmap

## Phase 1 — Foundation

* [x] Repository setup
* [ ] React frontend
* [ ] Express backend
* [ ] MongoDB connection
* [ ] Basic API structure

## Phase 2 — Authentication

* [ ] Registration
* [ ] Login
* [ ] JWT
* [ ] Protected routes
* [ ] Password reset

## Phase 3 — Organizations

* [ ] Organizations
* [ ] Members
* [ ] Roles
* [ ] Invitations

## Phase 4 — Projects

* [ ] Create projects
* [ ] Project dashboard
* [ ] Project members
* [ ] Project settings

## Phase 5 — Issues

* [ ] Create issues
* [ ] Edit issues
* [ ] Delete issues
* [ ] Labels
* [ ] Priority
* [ ] Assignees

## Phase 6 — Kanban

* [ ] Kanban board
* [ ] Drag and drop
* [ ] Status updates
* [ ] Filtering

## Phase 7 — Collaboration

* [ ] Comments
* [ ] Activity timeline
* [ ] Socket.IO
* [ ] Notifications

## Phase 8 — Analytics

* [ ] Project statistics
* [ ] Team workload
* [ ] Issue analytics
* [ ] Charts

## Phase 9 — Advanced Features

* [ ] GitHub integration
* [ ] Email notifications
* [ ] File uploads
* [ ] Markdown editor
* [ ] Advanced search
* [ ] Audit logs

## Phase 10 — Production

* [ ] Docker
* [ ] CI/CD
* [ ] Automated tests
* [ ] API documentation
* [ ] Security audit
* [ ] Production deployment

---

# 🔒 Security

OpenDesk follows common web application security practices.

The application will implement:

* Password hashing
* JWT authentication
* Role-based authorization
* Input validation
* API rate limiting
* CORS configuration
* HTTP security headers
* Environment variable protection
* MongoDB query validation
* File upload restrictions

---

# 🤝 Contributing

Contributions are welcome!

### 1. Fork the repository

```bash
git fork
```

### 2. Create a branch

```bash
git checkout -b feature/new-feature
```

### 3. Make your changes

```bash
git add .
git commit -m "feat: add new feature"
```

### 4. Push your branch

```bash
git push origin feature/new-feature
```

### 5. Create a Pull Request

Please provide:

* Description of the change
* Screenshots where applicable
* Testing information
* Related issue number

---

# 📜 License

This project is licensed under the **MIT License**.

---

# 👨‍💻 Author

Developed by **YOUR NAME**

GitHub:

https://github.com/YOUR_USERNAME

---

# ⭐ Support

If you find OpenDesk useful, consider giving the repository a ⭐ on GitHub.

---

# 📌 Project Goals

OpenDesk is more than a simple CRUD application.

The project aims to demonstrate practical implementation of:

```text
React
     ↓
REST APIs
     ↓
Express
     ↓
Node.js
     ↓
Mongoose
     ↓
MongoDB
```

along with:

```text
Authentication
Authorization
Real-time communication
File uploads
Kanban workflows
Notifications
Analytics
Testing
Docker
CI/CD
```

The goal is to build a realistic, scalable, open-source SaaS application while following modern full-stack development practices.

---

## 🚀 Built with the MERN Stack

**MongoDB • Express.js • React.js • Node.js**

⭐ Star the repository
🍴 Fork the project
🐛 Open an issue
🤝 Contribute
