# Claraa_Buddy
Clara Buddy is a web-based personalized study assistant that helps students plan their syllabus, study schedules, and timelines. It uses AI to generate study content and quizzes, checks if plans are realistic, and tracks progress to reduce academic stress and improve learning efficiency.

## 🚀 Getting Started

You can run this project in two modes:
1. **Browser Mode (Demo)**: Uses LocalStorage. No backend required.
2. **Full Stack Mode**: Uses Node.js + PostgreSQL to persist data.

---

### 📦 Prerequisites for Full Stack Mode

1. **Node.js**: Install from [nodejs.org](https://nodejs.org/).
2. **PostgreSQL**: Install from [postgresql.org](https://www.postgresql.org/download/).
3. **API Key**: A Google Gemini API key.

---

### 🛠️ Installation Guide

#### 1. Setup the Database (PostgreSQL)

1. Open your terminal or pgAdmin.
2. Create a new database named `clara_buddy`.
3. Run the SQL commands in `schema.sql` to create the tables.
   ```bash
   psql -U postgres -d clara_buddy -f schema.sql
   ```

#### 2. Setup the Backend Server

1. Open a terminal in the project root.
2. Initialize npm (if not done) and install dependencies:
   ```bash
   npm init -y
   npm install express pg cors bcrypt dotenv
   ```
3. Create a `.env` file in the root directory:
   ```env
   PORT=3001
   DB_USER=postgres
   DB_PASSWORD=your_password
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=clara_buddy
   ```
4. Start the server:
   ```bash
   node server.js
   ```
   You should see: `Server running on port 3001`.

#### 3. Connect Frontend to Backend

1. Open `services/authService.ts`.
2. Change the configuration at the top:
   ```typescript
   const USE_BACKEND = true; 
   ```
3. Run your React frontend (usually via `npm start` or your bundler command).

---

### 📂 Project Structure

- **src/components/**: React UI components (Dashboard, Quiz, etc.)
- **src/services/**: 
  - `geminiService.ts`: AI content generation.
  - `authService.ts`: Authentication handling (Local or API).
- **server.js**: The Express backend API.
- **schema.sql**: Database definitions.

### 🌟 Features

- **Micro-Learning Goals**: Break down syllabi into manageable chunks.
- **Confidence Tracking**: Log how you feel about subjects daily.
- **AI Tutors**: Personalized study guides and quizzes generated on the fly.
- **Secure Auth**: Password hashing with Bcrypt (in Full Stack mode).
