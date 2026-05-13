# 🚀 Habitor — CP & GATE Study Tracker

Habitor is a **full-stack productivity & analytics platform** built for **competitive programmers and GATE aspirants**.  
It helps you **track daily study sessions, maintain streaks, monitor syllabus progress, manage goals, and generate premium reports** — all in one place.

> “Consistency beats intensity. Habitor helps you stay consistent.”

---

## ✨ Features

### 📘 Study Log
- Log daily study sessions with **subject, topic, and hours**
- Automatically calculates:
  - Today’s study hours
  - Weekly study hours
  - Subject-wise distribution

### 🔥 Streak Tracking
- Automatically tracks:
  - **Current study streak**
  - **Best streak**
- Updates only when you study on a new day
- Resets correctly if a day is missed

### 📊 Analytics Dashboard
- Weekly bar charts
- Subject distribution pie chart
- Productivity percentage
- Clean, responsive UI

### 🎯 GATE Syllabus Tracker
- Topic-wise tracking for every GATE subject
- Auto-calculated **overall GATE progress (%)**
- Visual progress indicators

### 🏆 Goal Tracker
- Create long-term goals
- Update progress dynamically
- Completion animations & celebrations 🎉
- Auto-removal of completed goals

### 📄 Premium PDF Reports
- Export beautifully styled PDFs containing:
  - KPIs (Today, Weekly, Productivity)
  - Charts
  - Detailed study logs
- Perfect for **weekly review & accountability**

### 🌙 Dark / Light Mode
- Fully responsive
- Theme persists across sessions

### 🔐 Authentication & Cloud Sync
- Secure Firebase Authentication
- Real-time Firestore data sync
- User-specific data isolation

---

## 🛠 Tech Stack

### Frontend
- React
- Tailwind CSS
- Recharts

### Backend / Cloud
- Firebase Authentication
- Firebase Firestore

### Utilities
- jsPDF
- html2canvas

---

## 📁 Project Structure

src/
├── components/
│ ├── Navbar.jsx
│ ├── SkeletonCard.jsx
│ ├── StudyHeatmap.jsx
│
├── pages/
│ ├── Dashboard.jsx
│ ├── StudyLog.jsx
│ ├── GoalTracker.jsx
│ ├── GateTracker.jsx
│ ├── Profile.jsx
│
├── context/
│ └── ThemeContext.jsx
│
├── firebase/
│ └── config.js
│
├── utils/
│ └── achievementRules.js
│
└── App.jsx



---

## ⚙️ Environment Variables

Create a `.env` file in the root of your project:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id


🚀 Getting Started
1️⃣ Clone the Repository
git clone https://github.com/asdf-exe/Habitor.git
cd Habitor

2️⃣ Install Dependencies
npm install

3️⃣ Add Environment Variables

Create a .env file as shown above.

4️⃣ Run Locally
npm run dev
