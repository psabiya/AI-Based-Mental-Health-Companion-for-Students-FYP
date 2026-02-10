# Mental Health Chatbot & Mood Tracker

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![React](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-61dafb)
![Flask](https://img.shields.io/badge/Backend-Flask-black)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

> *A mental health support platform that helps students track moods, journal emotions, and chat with an AI companion in a safe and private environment.*

---

## 1. Introduction

This project aims to develop a **mental health support platform** that allows users to:
- track their daily mood,
- log emotional reflections,
- and converse with an AI chatbot for supportive, non-judgmental interaction.

The system is designed with **privacy, simplicity, and emotional safety** in mind, making it suitable for student well-being support.


**Key Features:**
*   **Mood Tracking:** Users can log their daily mood with emojis or text.
*   **AI Chatbot:** A supportive chat interface.
*   **Dashboard:** Visualizes mood trends over time using charts.
*   **Resource Access:** Provides access to mental health resources and helplines.
*   **Secure Auth:** JWT-based authentication for user privacy.


## 2. System Architecture

The system follows a standard Client-Server architecture.

### Frontend (Client)
*   **Framework:** React.js (Vite)
*   **Styling:** Tailwind CSS (for a clean, minimal aesthetic)
*   **State Management:** React Context API (for Auth and Theme)
*   **Routing:** React Router v6
*   **Charts:** Recharts (for mood visualization)
*   **Data Handling:** Axios (for API requests) / LocalStorage (for JWT)

### Backend (Server) - *Planned*
*   **Framework:** Python Flask (RESTful API)
*   **Database:** MongoDB or SQLite (for storing user data, mood logs, and chat history)
*   **AI Integration:** GroqCloud API (LLM for chat)
*   **NLP:** NLTK / Spacy (for sentiment analysis of mood logs) - Need to find a dataset possibly
*   **Authentication:** JWT (JSON Web Tokens)

### Data Flow
1.  **User Interaction:** User interacts with the React Frontend (Chat, Mood Input).
2.  **API Request:** Frontend sends secure HTTP requests (with JWT) to the Flask Backend.
3.  **Processing:**
    *   **Chat:** Backend sends prompt to an AI API and returns response.
    *   **Mood:** Backend analyzes sentiment (NLP) and stores data in DB.
4.  **Response:** Backend sends data back to Frontend for display (response message, updated charts).


## 3. Directory Structure

### Frontend (`/frontend`)
```
frontend/
├── public/
├── src/
│   ├── assets/          # Static images, icons
│   ├── components/      # Reusable UI components
│   │   ├── ui/          # Buttons, Inputs, Cards
│   │   ├── charts/      # Recharts wrappers
│   │   ├── layout/      # Navbar, Sidebar, Footer
│   │   └── chat/        # Chat bubbles, input area
│   ├── context/         # AuthContext, ThemeContext
│   ├── hooks/           # Custom React hooks (useAuth, useFetch)
│   ├── pages/           # Main route components
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   ├── Dashboard.jsx
│   │   ├── MoodTracker.jsx
│   │   └── Chat.jsx
│   ├── services/        # API service configuration (Axios)
│   ├── utils/           # Helper functions (date formatting)
│   ├── App.jsx          # Main App component with Routes
│   └── main.jsx         # Entry point
├── index.html
├── tailwind.config.js
└── vite.config.js
```

### Backend (`/backend`) - *Proposed*
```
backend/
├── app/
│   ├── __init__.py      # App factory
│   ├── routes/          # API blueprints
│   │   ├── auth.py      # Login/Register routes
│   │   ├── chat.py      # AI Chat routes
│   │   └── mood.py      # Mood tracking routes
│   ├── models/          # Database models
│   │   ├── user.py
│   │   └── mood_entry.py
│   ├── services/        # Business logic
│   │   ├── ai_service.py # GroqCloud integration
│   │   └── nlp_service.py # NLTK/Spacy logic
│   └── utils/           # Helper functions
├── config.py            # Environment configuration
├── requirements.txt     # Python dependencies
└── run.py               # Entry point
```
