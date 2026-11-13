# Run Beyond Limits 2026 — Setup & Seeding Guide

Welcome to the **Run Beyond Limits 2026 Marathon Platform (Edition 2)** setup guide. This document provides step-by-step instructions for database seeding, Nodemailer SMTP configuration, admin portal usage, and local execution.

- **GitHub Repository**: [https://github.com/JeevananthanV/marathon_event_2](https://github.com/JeevananthanV/marathon_event_2)
- **Author**: Jeevananthan V

---

## 📋 System Prerequisites

- **Node.js**: v18.0.0 or higher
- **npm** or **bun**
- **MongoDB**: Atlas connection string or local MongoDB URI
- **SMTP Account**: Gmail App Password or Mailtrap for email notifications

---

## 📥 1. Clone the Repository

```bash
git clone https://github.com/JeevananthanV/marathon_event_2.git
cd marathon_event_2
```

---

## ⚙️ 2. Environment Variables Configuration

### Backend Environment (`backend/.env`)

```env
PORT=5000
NODE_ENV=development
MONGODB_URI=your_mongodb_atlas_connection_string
JWT_SECRET=run_beyond_limits_jwt_secret_2026
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_gmail_app_password
CLIENT_URL=http://localhost:8080
DISABLE_WHATSAPP=true
```

### Frontend Environment (`marathon frontend/.env`)

```env
VITE_API_URL=http://localhost:5000
```

---

## 📦 3. Install Dependencies & Seed Database

```bash
# 1. Backend Setup & Seeding
cd backend
npm install
npm run seed       # Populates admin account + sample participants

# 2. Frontend Setup
cd "../marathon frontend"
npm install
cd ..
```

---

## 🚀 4. Running the Application Locally

### Terminal 1: Backend Server (Port 5000)

```bash
cd backend
npm run dev
```
Backend API will be listening at: `http://localhost:5000`

### Terminal 2: Frontend Client (Port 8080)

```bash
cd "marathon frontend"
npm run dev
```
Open your browser at: `http://localhost:8080`

---

## 🔐 5. Admin Panel Credentials

| Field | Value |
|---|---|
| **Admin Route** | `http://localhost:8080/admin` |
| **Username** | `admin` |
| **Password** | `password123` |

---

## 🏗️ 6. Production Build

```bash
cd "marathon frontend"
npm run build
```

---

## 🛠️ Troubleshooting

- **Admin login fails**: Run `npm run seed` inside `backend/` to regenerate the default administrator account.
- **Email sending fails**: Set `DISABLE_WHATSAPP=true` and confirm valid Gmail App Password in `SMTP_PASS`.
