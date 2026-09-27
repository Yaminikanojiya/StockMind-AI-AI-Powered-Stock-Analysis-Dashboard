# StockMind AI

**StockMind AI** is a full-stack stock analysis and market information platform built using **React.js** and **Python Flask**.

The application is designed to provide users with a structured dashboard for exploring stock market information, searching for stocks, viewing top gainers and losers, and managing their profiles.

The project is currently **under active development**, with additional financial analytics and AI-powered features being implemented.

---

##  Project Status

**Work in Progress**

The core frontend structure, routing, reusable components, and API communication setup have been implemented. More features are currently being developed, including advanced stock analytics and AI-based insights.

---

## ✨ Current Features

### 🔐 Authentication

* Login page
* User registration page
* JWT token handling
* Automatic authentication token attachment to API requests
* Unauthorized request handling

### 📊 Dashboard

The dashboard is designed to provide an overview of stock market information, including:

* Top Gainers
* Top Losers
* Stock information cards
* Market-related data

### 🔎 Stock Search

A dedicated search page is included for finding and exploring stock information.

### 👤 User Profile

A profile section is included for managing and displaying user-related information.

### 🧭 Application Navigation

The application uses React Router for navigation between:

* Dashboard
* Search
* Profile
* Login
* Register

### 🔗 API Integration

The frontend communicates with the backend using **Axios**.

The Axios configuration includes:

* Configurable API base URL using environment variables
* JSON request headers
* JWT authorization headers
* Request interceptors
* Response/error handling
* Automatic token removal on `401 Unauthorized`

---

## 🛠️ Tech Stack

### Frontend

* React.js
* JavaScript
* React Router
* Axios
* HTML5
* CSS3

### Backend

* Python
* Flask
* REST APIs

### Authentication

* JWT / Bearer Token Authentication
* Local Storage

### Development Tools

* Git
* GitHub
* VS Code
* Vite

---

## 🏗️ Application Architecture

```text
                    ┌─────────────────────┐
                    │       User          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   React.js Frontend │
                    ├─────────────────────┤
                    │ Dashboard           │
                    │ Search              │
                    │ Profile             │
                    │ Login / Register    │
                    └──────────┬──────────┘
                               │
                         Axios API
                               │
                         JWT Token
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Flask Backend     │
                    │      REST API       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Stock / User Data   │
                    └─────────────────────┘
```

---

## 📂 Project Structure

```text
StockMind-AI/
│
├── src/
│   │
│   ├── components/
│   │   ├── auth/
│   │   │   └── RegisterForm.jsx
│   │   │
│   │   ├── common/
│   │   │   └── Card.jsx
│   │   │
│   │   ├── dashboard/
│   │   │   ├── TopGainers.jsx
│   │   │   └── TopLosers.jsx
│   │   │
│   │   ├── Layout.jsx
│   │   ├── Navbar.jsx
│   │   ├── Sidebar.jsx
│   │   └── StockList.jsx
│   │
│   ├── pages/
│   │   ├── Login/
│   │   ├── Register/
│   │   ├── Dashboard/
│   │   ├── Search/
│   │   └── Profile/
│   │
│   ├── services/
│   │   └── axiosInstance.js
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── styles/
│       └── index.css
│
├── backend/
│   └── ...
│
├── package.json
├── .env
└── README.md
```

> The structure may change as the project continues to develop.

---

## 🔄 How the Application Works

### 1. User Authentication

Users can register or log in through the authentication pages.

After authentication, a token is stored locally and used for authenticated API requests.

### 2. API Communication

The React frontend communicates with the Flask backend using Axios.

The application uses an Axios instance with a configurable API URL:

```javascript
baseURL: import.meta.env.VITE_API_BASE_URL
```

If the environment variable is not configured, the application uses the local Flask API:

```text
http://localhost:5000/api
```

### 3. JWT Authentication

Whenever a token exists in local storage, Axios automatically attaches it to requests:

```text
Authorization: Bearer <token>
```

This allows protected backend endpoints to identify authenticated users.

### 4. Stock Dashboard

The dashboard uses reusable React components to display stock information.

For example:

* Top Gainers
* Top Losers
* Stock Cards
* Stock Lists

The components are designed to handle empty data states as well.

### 5. Routing

React Router manages the application routes:

```text
/login
/register
/dashboard
/search
/profile
```

The main application pages are rendered inside a reusable layout containing the Navbar and Sidebar.

---

##  Example Stock Data Structure

The stock components currently expect data in a structure similar to:

```javascript
{
  symbol: "AAPL",
  price: 227.16,
  changePercent: 2.45
}
```

This allows the same reusable components to display different stocks dynamically.

---

##  API Configuration

Create a `.env` file in the frontend project:

```env
VITE_API_BASE_URL=http://localhost:5000/api
```

The API URL can be changed depending on the backend environment.

---

## ⚙️ Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/StockMind-AI.git
cd StockMind-AI
```

### Install Frontend Dependencies

```bash
npm install
```

### Start the React Application

```bash
npm run dev
```

The frontend will run using the Vite development server.

---

## Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Create a Python virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask backend:

```bash
python app.py
```

The backend will be available through the configured Flask API URL.

 Planned Features

Since the project is still under development, the following features are planned:

 AI-powered stock question answering
   RAG-based financial information retrieval
   Advanced stock analytics
   Interactive stock charts
   Improved stock search
   Financial news integration
   AI-generated stock insights
   Historical stock analysis
   Enhanced user profile and preferences
   Improved responsive design
   Improved authentication and authorization
   Deployment of frontend and backend

---

 Future Vision

The long-term goal of **StockMind AI** is to combine traditional stock-market data with AI-based analysis to create an interactive platform where users can explore financial information through a simple dashboard and ask questions about market data.

Potential interactions could include:

```text
User:
"Show me the top gaining stocks."

        ↓

StockMind AI

        ↓

Market Data + Analysis

        ↓

Dashboard Result
```

And eventually:

```text
User:
"What happened to this stock recently?"

        ↓

AI + RAG Pipeline

        ↓

Relevant Financial Data

        ↓

AI-Generated Explanation


## 📚 Learning Outcomes

This project is helping me gain practical experience with:

* React.js component development
* React Router
* Reusable UI components
* REST API integration
* Axios
* JWT authentication
* Frontend-backend communication
* Python Flask
* Stock market data handling
* Application architecture
* Git and GitHub
* Full-stack application development


StockMind AI is an actively developing project. More features and improvements will be added as development continues.
