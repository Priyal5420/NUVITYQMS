# =========================================
# NUVITYQMS FULL STACK SaaS APPLICATION
# =========================================

# TECHNOLOGY STACK

Frontend:
- React.js
- Tailwind CSS
- Vite

Backend:
- Node.js
- Express.js

Database:
- PostgreSQL

Authentication:
- JWT Authentication

Hosting:
- Frontend → Vercel
- Backend → Render
- Database → Supabase

# =========================================
# PROJECT STRUCTURE
# =========================================

nuvityqms/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── layouts/
│   │   ├── services/
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── backend/
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── config/
│   ├── server.js
│   └── package.json
│
└── README.md

# =========================================
# FRONTEND SETUP
# =========================================

# Create Frontend

npm create vite@latest frontend

cd frontend

npm install

# Install Dependencies

npm install react-router-dom axios tailwindcss

# =========================================
# TAILWIND SETUP
# =========================================

npm install -D tailwindcss postcss autoprefixer

npx tailwindcss init -p

# tailwind.config.js

export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

# =========================================
# MAIN PAGES
# =========================================

Public Pages:
- Home
- About
- Pricing
- Contact
- Demo Request

Customer Pages:
- Login
- Dashboard
- CAPA Tracker
- Audit Module
- Document Control
- Notifications

# =========================================
# LOGIN PAGE
# src/pages/Login.jsx
# =========================================

import { useState } from 'react'
import axios from 'axios'

export default function Login() {

  const [email, setEmail] = useState('')
  const [password, setPassword] = useState('')

  const handleLogin = async () => {

    const response = await axios.post(
      'http://localhost:5000/api/login',
      {
        email,
        password,
      }
    )

    localStorage.setItem('token', response.data.token)
  }

  return (
    <div className='min-h-screen flex items-center justify-center bg-gray-100'>

      <div className='bg-white p-8 rounded-2xl shadow-lg w-96'>

        <h1 className='text-3xl font-bold mb-6 text-center'>
          NUVITYQMS Login
        </h1>

        <input
          type='email'
          placeholder='Email'
          className='w-full border p-3 rounded-xl mb-4'
          onChange={(e) => setEmail(e.target.value)}
        />

        <input
          type='password'
          placeholder='Password'
          className='w-full border p-3 rounded-xl mb-4'
          onChange={(e) => setPassword(e.target.value)}
        />

        <button
          onClick={handleLogin}
          className='w-full bg-blue-900 text-white py-3 rounded-xl'
        >
          Login
        </button>

      </div>
    </div>
  )
}

# =========================================
# DASHBOARD CARD
# =========================================

<div className='grid grid-cols-4 gap-6'>

  <div className='bg-white p-6 rounded-2xl shadow'>

    <h2>Open CAPA</h2>

    <p className='text-4xl font-bold'>07</p>

  </div>

</div>

# =========================================
# BACKEND SETUP
# =========================================

mkdir backend

cd backend

npm init -y

# Install Packages

npm install express cors dotenv pg bcrypt jsonwebtoken

# =========================================
# BACKEND SERVER
# server.js
# =========================================

const express = require('express')
const cors = require('cors')

const app = express()

app.use(cors())
app.use(express.json())

app.get('/', (req, res) => {
  res.send('NUVITYQMS API Running')
})

app.listen(5000, () => {
  console.log('Server running on port 5000')
})

# =========================================
# DATABASE TABLES
# =========================================

# Company Table

CREATE TABLE companies (

  id SERIAL PRIMARY KEY,

  company_name VARCHAR(255),

  industry VARCHAR(255),

  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP

);

# Users Table

CREATE TABLE users (

  id SERIAL PRIMARY KEY,

  company_id INTEGER REFERENCES companies(id),

  name VARCHAR(255),

  email VARCHAR(255) UNIQUE,

  password VARCHAR(255),

  role VARCHAR(50)

);

# CAPA Table

CREATE TABLE capa (

  id SERIAL PRIMARY KEY,

  company_id INTEGER REFERENCES companies(id),

  issue TEXT,

  root_cause TEXT,

  corrective_action TEXT,

  target_date DATE,

  status VARCHAR(50)

);

# =========================================
# MULTI COMPANY SaaS LOGIC
# =========================================

Every table must include:

company_id

This ensures:
- Company A sees only Company A data
- Company B sees only Company B data

Example:

SELECT * FROM capa
WHERE company_id = 1;

# =========================================
# JWT LOGIN TOKEN
# =========================================

const jwt = require('jsonwebtoken')

const token = jwt.sign(

  {
    userId: user.id,
    companyId: user.company_id,
  },

  process.env.JWT_SECRET,

  {
    expiresIn: '7d',
  }

)

# =========================================
# PHASE 1 MODULES
# =========================================

1. Dashboard
2. Document Control
3. Audit Management
4. CAPA Management
5. Notifications

# =========================================
# PHASE 2 MODULES
# =========================================

1. Lean Module
2. Training Module
3. Maintenance Module
4. ZED Assessment

# =========================================
# PHASE 3 MODULES
# =========================================

1. AI Draft Generator
2. ERP Integration
3. Mobile App
4. Analytics

# =========================================
# GITHUB UPLOAD
# =========================================

git init

git add .

git commit -m "Initial Commit"

git branch -M main

git remote add origin YOUR_GITHUB_LINK

git push -u origin main

# =========================================
# FRONTEND DEPLOYMENT
# =========================================

https://vercel.com

Deploy frontend from GitHub.

Example Live Link:

https://nuvityqms.vercel.app

# =========================================
# BACKEND DEPLOYMENT
# =========================================

https://render.com

Deploy backend service.

# =========================================
# ENV FILE
# =========================================

PORT=5000

DATABASE_URL=YOUR_DATABASE_URL

JWT_SECRET=YOUR_SECRET_KEY

# =========================================
# CUSTOMER FEATURES
# =========================================

- Company Dashboard
- Audit Tracking
- CAPA Tracking
- SOP Repository
- Notifications
- User Management

# =========================================
# ADMIN FEATURES
# =========================================

- Manage All Companies
- Subscription Tracking
- Customer Onboarding
- Support Management

# =========================================
# PRICING
# =========================================

Basic:
₹999/month

Professional:
₹2999/month

Enterprise:
Custom Pricing

# =========================================
# FUTURE INTEGRATIONS
# =========================================

- WhatsApp Alerts
- Email Notifications
- QR Tracking
- AI Suggestions
- Gujarati Language
- Hindi Language

# =========================================
# SECURITY
# =========================================

- Password Hashing
- JWT Authentication
- HTTPS
- Database Backup
- Role Permissions

# =========================================
# DOMAIN SUGGESTIONS
# =========================================

- nuvityqms.com
- nuvityqms.in
- smartqms.in

# =========================================
# FINAL BUSINESS MODEL
# =========================================

You Can Sell:
- SaaS Subscription
- ISO Consulting
- Lean Consulting
- Audit Services
- Training Services
- ZED Consulting

# =========================================
# FINAL GOAL
# =========================================

NUVITYQMS =
Smart + Easy + MSME Friendly

Multi-company SaaS Platform
for ISO + Lean + MSME Management.
