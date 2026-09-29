# 🤖 AI StudyBuddy

AI StudyBuddy is an AI-powered learning platform designed to help students learn more effectively from their study materials.

The application allows students to upload study materials and automatically generate summaries, flashcards, quizzes, and personalized study plans using the Google Gemini API.

---

## 📌 Overview

AI StudyBuddy combines modern web technologies and Generative AI to provide an intelligent and personalized learning experience.

The system provides:

- Secure user authentication
- Study material management
- AI-generated summaries
- AI-generated flashcards
- AI-generated quizzes
- Personalized AI study plans
- Role-Based Access Control
- MongoDB data storage

---

## ✨ Features

### 🔐 Secure User Authentication

- User registration and login
- JWT-based authentication
- Password hashing using bcrypt
- Protected API routes
- Secure access to user resources

### 📚 Study Material Management

- Upload study materials
- Add title and subject
- Store study content in MongoDB
- View previously uploaded materials
- Manage personal study resources

### 📝 AI Summary Generation

Generates concise and easy-to-understand summaries from uploaded study materials using the Google Gemini API.

### 🧠 AI Flashcard Generation

Automatically creates question-and-answer flashcards from study materials to support revision and active recall.

### ❓ AI Quiz Generation

Generates multiple-choice questions based on uploaded study content, allowing students to test their knowledge.

### 📅 AI Study Plan Generation

Creates personalized study plans based on study materials and examination dates.

### 👥 Role-Based Access Control

The system supports two user roles:

- Student
- Administrator

Each role has different permissions and access levels.

### 🗄️ MongoDB Data Storage

MongoDB stores:

- User information
- Study materials
- Summaries
- Flashcards
- Quizzes
- Study plans

---

## 🏗️ System Architecture

```text
                    React.js Client
                          |
                          v
                    REST API
                          |
                          v
                  Express.js Server
                          |
                 +--------+--------+
                 |                 |
                 v                 v
          JWT Authentication    API Routes
                                   |
                                   v
                              Controllers
                                   |
                         +---------+---------+
                         |                   |
                         v                   v
                    MongoDB            Gemini AI
                         |                   |
                         |                   v
                         |            AI Generated
                         |             Resources
                         |                   |
                         +---------+---------+
                                   |
                                   v
                              JSON Response
                                   |
                                   v
                              React Client
🛠️ Technologies Used
Technology	Purpose
React.js	Frontend
Node.js	Backend Runtime
Express.js	REST API Framework
MongoDB	Database
Mongoose	MongoDB ODM
JWT	Authentication
bcrypt.js	Password Hashing
Google Gemini API	AI Content Generation
REST API	Client-Server Communication
📂 Project Structure
AI-StudyBuddy/
│
├── client/
│   └── React.js frontend
│
├── server/
│   │
│   ├── config/
│   │   └── db.js
│   │
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── studyController.js
│   │   ├── aiController.js
│   │   └── adminController.js
│   │
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   └── roleMiddleware.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   ├── StudyMaterial.js
│   │   ├── Summary.js
│   │   ├── Flashcard.js
│   │   ├── Quiz.js
│   │   └── StudyPlan.js
│   │
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── studyRoutes.js
│   │   ├── aiRoutes.js
│   │   └── adminRoutes.js
│   │
│   ├── services/
│   │   └── geminiService.js
│   │
│   ├── server.js
│   ├── package.json
│   └── .env
│
└── README.md
🔄 User Flow
Start
  |
  v
Register / Login
  |
  v
JWT Authentication
  |
  v
Dashboard
  |
  v
Upload Study Material
  |
  v
Select AI Feature
  |
  +----> Summary
  |
  +----> Flashcards
  |
  +----> Quiz
  |
  +----> Study Plan
  |
  v
Google Gemini API
  |
  v
Generated Learning Resource
  |
  v
MongoDB
  |
  v
Display Result
👥 User Roles
Student

Students can:

Register and log in
Upload study materials
View study materials
Generate AI summaries
Generate AI flashcards
Generate AI quizzes
Generate personalized study plans
View previously generated resources
Manage their own learning materials
Administrator

Administrators can:

Log in securely
View registered users
Manage user accounts
Monitor system usage
Perform system-level operations
🗃️ Database

The application uses MongoDB with Mongoose.

Collections
users
studymaterials
summaries
flashcards
quizzes
studyplans
Database Relationships
User
 |
 +----< StudyMaterial
 |          |
 |          +----< Summary
 |          |
 |          +----< Flashcard
 |          |
 |          +----< Quiz
 |
 +----< StudyPlan
🔑 Environment Variables

Create a .env file inside the backend directory.

PORT=5000

MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

GEMINI_API_KEY=your_gemini_api_key

Important: Never commit your .env file or API keys to GitHub.

Add the following to .gitignore:

node_modules/
.env
⚙️ Installation
1. Clone the Repository
git clone YOUR_REPOSITORY_URL
2. Navigate to the Project
cd AI-StudyBuddy
3. Install Backend Dependencies
cd server
npm install
4. Configure Environment Variables

Create a .env file and add:

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
GEMINI_API_KEY=your_gemini_api_key
5. Start the Backend
npm start

For development:

npm run dev

The backend will run on:

http://localhost:5000
🌐 API Endpoints
Authentication
POST /api/auth/register
POST /api/auth/login
Study Materials
GET    /api/study
POST   /api/study
DELETE /api/study/:id
AI Services
GET /api/ai/summary/:id
GET /api/ai/flashcards/:id
GET /api/ai/quiz/:id
GET /api/ai/study-plan/:id
Administration
GET    /api/admin/users
GET    /api/admin/users/:id
DELETE /api/admin/users/:id
🔒 Security

AI StudyBuddy implements the following security mechanisms:

JWT-based authentication
bcrypt password hashing
Protected API routes
Role-Based Access Control
Environment-based API key management
User-specific data access
Password exclusion from API responses
🤖 AI Processing

The AI service communicates with the Google Gemini API to generate learning resources.

Study Material
      |
      v
AI Controller
      |
      v
Gemini Service
      |
      v
Google Gemini API
      |
      v
Generated Content
      |
      v
MongoDB / Client

The AI service generates:

Summaries
Flashcards
Quizzes
Study Plans
🎥 Demo

The project demonstration includes:

User Registration
User Login
Student Dashboard
Study Material Upload
AI Summary Generation
AI Flashcard Generation
AI Quiz Generation
AI Study Plan Generation
Saved Learning Resources
Administrator Login
User Management
MongoDB Data Storage
🚀 Future Enhancements

Future versions of AI StudyBuddy may include:

PDF and DOCX file upload
Voice-based learning assistant
Learning progress tracking
Student performance analytics
Difficulty-based quiz generation
Notifications and reminders
Multi-language AI responses
Real-time study recommendations
Mobile application
Advanced administrator dashboard
🎯 Project Objective

The main objective of AI StudyBuddy is to provide students with an intelligent learning assistant that transforms their study materials into useful learning resources.

By using Generative AI, the system reduces the effort required to manually create summaries, flashcards, quizzes, and study schedules.

👨‍💻 Project Information

Project Name: AI StudyBuddy

Project Type: AI-Powered Learning Platform

Frontend: React.js

Backend: Node.js + Express.js

Database: MongoDB

Authentication: JWT

AI Service: Google Gemini API

Architecture: Modular RESTful Architecture
