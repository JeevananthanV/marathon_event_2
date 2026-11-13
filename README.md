# 🏃 Run Beyond Limits 2026 — Marathon Event Management System

[![Repository](https://img.shields.io/badge/GitHub-JeevananthanV%2Fmarathon__event__2-blue?logo=github)](https://github.com/JeevananthanV/marathon_event_2)
[![React](https://img.shields.io/badge/React-19.0-61DAFB?logo=react&logoColor=white)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Node.js](https://img.shields.io/badge/Node.js-v18+-339933?logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/atlas)

A full-stack marathon event registration and management platform for **Run Beyond Limits 2026** — a multi-city running event held simultaneously across **Chennai, Bengaluru, and Salem**.

---

## 🔗 Repository & Links

| Detail | Link |
|---|---|
| **GitHub Repository** | [https://github.com/JeevananthanV/marathon_event_2](https://github.com/JeevananthanV/marathon_event_2) |
| **Author** | [Jeevananthan V](https://github.com/JeevananthanV) |
| **Admin Route** | `/admin` |
| **Demo Credentials** | Username: `admin` / Password: `password123` |

---

## ✨ Key Features

### 🏃 Runner Portal
- Multi-step registration form with real-time Zod schema validation
- Race category selection (5K / 10K / Half Marathon) with T-shirt size picker
- Confirmation email with PDF certificate sent automatically on payment approval
- Certificate download page — lookup by email or phone number

### 🔐 Admin Dashboard
- **Dashboard Overview** — Live stats: total registrations, revenue, payment breakdown, category distribution
- **Participants Table** — Search, filter, sort, and paginate all registered runners
- **Payment Management** — Approve/reject payments; auto-generates BIB numbers on approval
- **T-Shirt Management** — Track T-shirt size allocations per runner
- **Reports & Exports** — Download participant data as CSV/Excel reports
- **Contacts** — View and manage contact form submissions
- **Light / Dark Theme** — Toggle between themes; preference saved in localStorage
- Secure JWT-based authentication with session persistence

### 📧 Automation
- Styled HTML confirmation emails via Nodemailer (Gmail SMTP)
- Dynamically generated PDF certificates with QR code validation
- Automatic BIB number assignment upon payment approval

### 🗺️ Multi-City Support
- **Chennai** — Marina Beach coastal route
- **Bengaluru** — Vidhana Soudha heritage route
- **Salem** — Yercaud scenic hills route

---

## 📁 Project Structure

```
Marathon_Event_2/
├── backend/
│   ├── config/          # MongoDB connection & env setup
│   ├── controllers/     # Route logic (auth, participants, payments, contacts)
│   ├── middleware/      # JWT auth, error handlers
│   ├── models/          # Mongoose models (Participant, User, Contact)
│   ├── routes/          # Express route declarations
│   ├── services/        # Email (Nodemailer), PDF generation
│   ├── seeds/           # Database seed scripts
│   └── server.js        # Express application entry
│
└── marathon frontend/
    ├── src/
    │   ├── components/  # Reusable UI components & admin views
    │   ├── pages/       # Route pages (Home, Register, Certificate, Admin)
    │   ├── context/     # Auth & theme context
    │   └── utils/       # API client & helpers
    └── package.json
```

---

## 🚀 Local Setup

### Clone Repository

```bash
git clone https://github.com/JeevananthanV/marathon_event_2.git
cd marathon_event_2
```

### 1. Backend Setup

Create `backend/.env`:
```env
PORT=5000
MONGODB_URI=your_mongodb_atlas_uri
JWT_SECRET=your_jwt_secret
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_gmail_app_password
CLIENT_URL=http://localhost:8080
```

```bash
cd backend
npm install
npm run seed     # Seeds admin + test participants
npm run dev      # Starts API at http://localhost:5000
```

### 2. Frontend Setup

Create `marathon frontend/.env`:
```env
VITE_API_URL=http://localhost:5000
```

```bash
cd "marathon frontend"
npm install
npm run dev      # Starts site at http://localhost:8080
```

---

## 👨‍💻 Author

**Jeevananthan V** — [@JeevananthanV](https://github.com/JeevananthanV)

## License

MIT
