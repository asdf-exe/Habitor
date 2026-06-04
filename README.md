<div align="center">

# 🚀 Habitor — CP & GATE Study Tracker

[![React](https://img.shields.io/badge/React-18.x-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-5.x-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.x-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![NodeJS](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-8.x-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

**A full-stack productivity, study analytics & progress tracking platform tailored for Competitive Programmers and GATE Aspirants.**

> *"Consistency beats intensity. Habitor empowers you to build non-negotiable daily habits and track long-term academic growth."*

</div>

---

## 🌟 Key Features

| Feature | Description |
| :--- | :--- |
| 📘 **Daily Study Log & Heatmap** | Record daily study hours with subject and topic tagging. Features a GitHub-style activity contribution grid. |
| 🔥 **Streak Engine** | Automated study streak counter that calculates current and longest streak while handling rest days gracefully. |
| 📊 **Interactive Analytics** | Real-time charts powered by Recharts visualizing weekly distributions and subject breakdown. |
| 🎯 **GATE Exam Tracker** | Comprehensive GATE CS/IT syllabus breakdown with topic-level checkboxes and progress metrics. |
| 🏆 **Goals & Achievements** | Define short-term & long-term targets, earning gamified milestone badges as you reach study goals. |
| 📈 **Codeforces Visualizer** | Seamless Codeforces rating progression chart and contest performance tracking. |
| 🌙 **Theme & Personalization** | Sleek Dark / Light mode toggle with persistent local preferences and custom user profiles. |

---

## 🌐 System Architecture

```text
               +-----------------------------------+
               |       Client Side (React / Vite)   |
               |  TailwindCSS | Recharts | Context  |
               +-----------------+-----------------+
                                 |
                                 | HTTP / REST API (Axios + JWT)
                                 v
               +-----------------+-----------------+
               |      Express Node.js Server       |
               |  Auth Middleware | Controllers    |
               +-----------------+-----------------+
                                 |
                                 v
               +-----------------+-----------------+
               |       Database (MongoDB Atlas)     |
               |  Users, StudyLogs, Goals, GATE... |
               +-----------------------------------+
```

---

## 🔌 API Endpoints Reference

### 🔐 Authentication (`/api/auth`)
- `POST /api/auth/register` — Register a new account
- `POST /api/auth/login` — Authenticate user and issue JWT token
- `GET /api/auth/me` — Retrieve current authenticated user profile
- `PUT /api/auth/profile` — Update target exam and profile preferences

### 📘 Study Logs (`/api/study-logs`)
- `POST /api/study-logs` — Create a new study log entry
- `GET /api/study-logs` — Fetch user's study log history
- `GET /api/study-logs/stats` — Retrieve aggregated study stats & heatmap data

### 🎯 Goal Tracker (`/api/goals`)
- `GET /api/goals` — List all user goals
- `POST /api/goals` — Create a target goal
- `PUT /api/goals/:id` — Update goal completion status
- `DELETE /api/goals/:id` — Remove a goal

### 🎓 GATE Progress (`/api/gate-progress`)
- `GET /api/gate-progress` — Fetch topic completion status across syllabus
- `PUT /api/gate-progress` — Toggle topic completion status

### 📈 Codeforces & Achievements (`/api/cf-rating`, `/api/achievements`)
- `GET /api/cf-rating` — Get current CF rating history
- `POST /api/cf-rating/sync` — Sync rating with Codeforces API
- `GET /api/achievements` — Fetch unlocked user achievement badges

---

## 🛠 Tech Stack

- **Frontend**: React 18, Vite, TailwindCSS, Recharts, Lucide Icons, Axios, Firebase Auth SDK
- **Backend**: Node.js, Express.js, MongoDB, Mongoose, JWT (JSON Web Tokens), bcryptjs
- **Tooling**: ESLint, PostCSS, Git

---

## 📁 Project Structure

```text
Habitor/
├── backend/
│   ├── src/
│   │   ├── config/          # MongoDB Connection setup
│   │   ├── controllers/     # Controller business logic
│   │   ├── middleware/      # JWT Authentication Guard
│   │   ├── models/          # Mongoose Schemas (User, StudyLog, Goal, GATE...)
│   │   ├── routes/          # Express Router Definitions
│   │   └── server.js        # Server Entry Point
│   └── package.json
└── frontend/
    ├── src/
    │   ├── api/             # Axios Instance & Interceptors
    │   ├── components/      # Navbar, Heatmap, Skeleton, Charts, Toggle
    │   ├── context/         # AuthContext & ThemeContext Providers
    │   ├── data/            # GATE Syllabus Dataset
    │   ├── firebase/        # Firebase Client SDK Configuration
    │   ├── pages/           # Landing, Login, Dashboard, Trackers, Profile
    │   ├── utils/           # Achievement Rules & Calculators
    │   ├── App.jsx          # Route Definitions & Layout Wrappers
    │   └── main.jsx         # DOM Mounting Point
    └── package.json
```

---

## ⚡ Quickstart & Installation

### Prerequisites
- Node.js (v18.0.0 or higher)
- npm or yarn
- MongoDB Atlas Database connection URI

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/asdf-exe/Habitor.git
cd Habitor
```

### 2️⃣ Backend Setup
```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` directory:
```env
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/habitor
JWT_SECRET=your_super_secret_jwt_key
CLIENT_ORIGIN=http://localhost:5173
```

Start the backend development server:
```bash
npm run dev
```

### 3️⃣ Frontend Setup
```bash
cd ../frontend
npm install
```

Create a `.env` file in the `frontend/` directory:
```env
VITE_API_URL=http://localhost:5000/api
VITE_FIREBASE_API_KEY=your_firebase_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_messaging_id
VITE_FIREBASE_APP_ID=your_app_id
```

Start the Vite development server:
```bash
npm run dev
```

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

<div align="center">
Built with ❤️ for student consistency & competitive growth.
</div>
