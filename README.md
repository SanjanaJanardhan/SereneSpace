# SereneSpace

A full-stack mental wellness app built with the MERN stack. Users can log journal entries, track their mood over time, and unwind with a wellness trivia game — all behind a personal account with JWT-based auth.

---

## Features

- **Authentication** — secure signup and login with JWT; passwords hashed with bcrypt
- **Journaling** — create and view personal journal entries tied to your account
- **Mood Tracker** — log your mood daily and visualize trends over time with Chart.js
- **Wellness Trivia** — answer reflective questions pulled from a curated question bank
- **REST API** — clean separation between frontend and backend with dedicated route files for users, journals, moods, and questions

---

## Tech Stack

**Frontend**
- React 18, React Router v6
- Axios for API calls
- Chart.js / react-chartjs-2 for mood visualization
- date-fns for date handling

**Backend**
- Node.js + Express
- MongoDB with Mongoose
- JWT for auth, bcrypt for password hashing
- dotenv for environment config

---

## Project Structure

```
SereneSpace/
├── SereneSpace_Node/        # Express backend
│   ├── config/db.js         # MongoDB connection
│   ├── models/              # Mongoose schemas (User, Journal, MoodTracker, Questions)
│   ├── routes/              # REST endpoints
│   └── server.js            # Entry point, runs on port 5000
│
└── SereneSpace_React/       # React frontend
    └── serenespace/
        ├── public/
        └── src/
            ├── components/  # Header, MoodPlot, JournalSummary, UserForm
            ├── pages/       # Login, Signup, Journal, MoodTracker, Trivia, Main
            └── services/    # API service layer
```

---

## Getting Started

### Prerequisites
- Node.js
- MongoDB running locally

### Backend
```bash
cd SereneSpace_Node
npm install
```

Create a `.env` file in `SereneSpace_Node/`:
```
MONGO_URI=mongodb://127.0.0.1:27017/SereneSpace
```

```bash
node server.js
# Server runs on http://localhost:5000
```

### Frontend
```bash
cd SereneSpace_React/serenespace
npm install
npm start
# App runs on http://localhost:3000
```

---

## API Routes

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/users/register` | Register a new user |
| POST | `/api/users/login` | Login and receive JWT |
| GET/POST | `/api/journals` | Fetch or create journal entries |
| GET/POST | `/api/moods` | Fetch or log mood entries |
| GET | `/api/questions` | Fetch trivia questions |
