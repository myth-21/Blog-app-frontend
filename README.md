# Blog App

A full-stack blog application built with React, Express.js, and MongoDB. Features user authentication, role-based access control, article management, and an admin dashboard.

![React](https://img.shields.io/badge/React-19.2.0-blue.svg)
![Express.js](https://img.shields.io/badge/Express.js-5.2.1-green.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-8.0-red.svg)
![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)

---

#  Features

##  User Management
- Secure User Registration & Login
- JWT Authentication
- Role-Based Access Control
- Profile Management
- Image Upload Support

## Content Management
- Create & Publish Articles
- Edit/Delete Articles
- Rich Text Content
- Category Support
- Comment System

##  Admin Dashboard
- User Management
- Block/Unblock Users
- Activate/Deactivate Articles
- Dashboard Analytics
- Full Administrative Control

##  User Interface
- Modern Apple-Inspired UI
- Responsive Design
- Protected Routes
- Toast Notifications
- Mobile Friendly

---

#  Repository Structure

```bash
blog-app/
├── backend/
│   ├── APIs/
│   │   ├── AdminAPI.js
│   │   ├── AuthorAPI.js
│   │   ├── UserAPI.js
│   │   └── CommonAPI.js
│   ├── config/
│   ├── middlewares/
│   ├── models/
│   ├── services/
│   └── server.js
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── store/
│   │   ├── styles/
│   │   └── main.jsx
│   └── package.json
│
└── README.md
```

---

# Tech Stack

## Frontend
- React 19
- React Router DOM
- Zustand
- Tailwind CSS
- Axios
- React Hook Form
- React Hot Toast

## Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- bcryptjs
- Cloudinary
- Multer
- CORS

---

#  Prerequisites

Before running the application, install:

- Node.js (v18 or higher)
- MongoDB
- npm or yarn

---

#  Install Required Packages

##  Backend Setup

Move to backend folder:

```bash
cd backend
```

### Install Backend Dependencies

```bash
npm install express mongoose cors dotenv bcryptjs jsonwebtoken cloudinary multer cookie-parser
```

### Install Development Dependencies

```bash
npm install -D nodemon
```

---

##  Frontend Setup

Move to frontend folder:

```bash
cd frontend
```

### Install Frontend Dependencies

```bash
npm install react-router-dom axios zustand react-hot-toast react-hook-form
```

### Install Tailwind CSS

```bash
npm install -D tailwindcss @tailwindcss/vite
```

---

#  Tailwind CSS Configuration

## Update `vite.config.js`

```javascript
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react(), tailwindcss()],
})
```

## Add Tailwind Import in `src/index.css`

```css
@import "tailwindcss";
```

---

#  Quick Start

## 1️ Clone the Repository

```bash
git clone https://github.com/BAIKANI-MANASA/Blog-App.git
cd blog-app
```

---

## 2️ Backend Environment Setup

Move to backend:

```bash
cd backend
```

Create `.env` file:

```bash
cp .env.example .env
```

### Windows PowerShell

```powershell
copy .env.example .env
```

---

## 3️ Configure Environment Variables

Create `.env` inside backend:

```env
# Database
DB_URL=mongodb://localhost:27017/blog-backend

# Server
PORT=4000

# JWT Secret
JWT_SECRET=your-secret-key

# Cloudinary
CLOUD_NAME=your-cloudinary-name
API_KEY=your-cloudinary-api-key
API_SECRET=your-cloudinary-api-secret
```

---

#  Running the Application

## Start Backend Server

```bash
cd backend
npm start
```

Backend runs on:

```bash
http://localhost:4000
```

---

## Start Frontend Development Server

```bash
cd frontend
npm run dev
```

Frontend runs on:

```bash
http://localhost:5173
```

---

#  Default Admin Account

Run this in MongoDB shell:

```javascript
db.users.insertOne({
  firstName: "admin",
  lastName: "admin",
  role: "ADMIN",
  email: "admin@mail.com",
  password: "$2a$12$zBYi4VNPbfV1qhe78SnujeiDkZ1.RkYDO6kTLx4MAj3Sshbw/cr5u",
  isActive: true,
  createdAt: new Date(),
  updatedAt: new Date()
})
```

## Admin Login

```bash
Email: admin@mail.com
Password: admin
```

---

#  User Roles

| Role | Permissions |
|------|-------------|
| USER | Read Articles & Comment |
| AUTHOR | Create/Edit/Delete Own Articles |
| ADMIN | Full System Access |

---

#  API Endpoints

## Authentication APIs

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/common-api/login` | Login User |
| POST | `/common-api/logout` | Logout User |
| GET | `/common-api/check-auth` | Check Auth Status |

---

## User APIs

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/user-api/users` | Register User |
| GET | `/user-api/articles` | Get Articles |
| GET | `/user-api/article/:id` | Get Single Article |
| PUT | `/user-api/articles` | Add Comment |

---

## Author APIs

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/author-api/users` | Register Author |
| POST | `/author-api/articles` | Create Article |
| GET | `/author-api/articles/:authorId` | Get Author Articles |
| PUT | `/author-api/articles` | Update Article |

---

## Admin APIs

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/admin-api/dashboard/stats` | Dashboard Stats |
| GET | `/admin-api/users` | Get Users |
| GET | `/admin-api/articles` | Get Articles |
| PUT | `/admin-api/users/block/:userId` | Block User |
| PUT | `/admin-api/users/unblock/:userId` | Unblock User |
| PUT | `/admin-api/articles/activate/:articleId` | Activate Article |
| PUT | `/admin-api/articles/deactivate/:articleId` | Deactivate Article |

---

#  Production Build

## Frontend Build

```bash
cd frontend
npm run build
```

---

## Backend Start

```bash
cd backend
npm start
```

---

#  Deploy Frontend on Vercel

## 1️ Install Vercel CLI

```bash
npm install -g vercel
```

---

## 2️ Login to Vercel

```bash
vercel login
```

---

## 3️ Move to Frontend Folder

```bash
cd frontend
```

---

## 4️ Deploy Project

```bash
vercel
```

During setup:

### Framework

```bash
Vite
```

### Build Command

```bash
npm run build
```

### Output Directory

```bash
dist
```

---

## 5️ Production Deployment

```bash
vercel --prod
```

---

#  Frontend Environment Variables

Create `.env` inside frontend:

```env
VITE_API_URL=http://localhost:4000
```

For production:

```env
VITE_API_URL=https://blog-app-pvm9.onrender.com
```

---

#  Axios Configuration Example

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: import.meta.env.VITE_API_URL,
});

export default api;
```

---

#  Optional Vercel Configuration

Create `vercel.json` inside frontend:

```json
{
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/"
    }
  ]
}
```

This helps React Router work properly after deployment.

---

# Useful Vercel Commands

## Redeploy Project

```bash
vercel --prod
```

## View Linked Projects

```bash
vercel project ls
```

## Remove Deployment

```bash
vercel remove
```

## Logout from Vercel

```bash
vercel logout
```

---

#  Recommended Deployment Flow

1. Deploy Backend
2. Copy Backend Production URL
3. Add Backend URL in Frontend `.env`
4. Deploy Frontend on Vercel
5. Test Authentication & APIs

---

#  License

This project is licensed under the ISC License.

---

#  Acknowledgments

- React
- Express.js
- MongoDB
- Tailwind CSS
- Vercel

---

#  Support

If you have any questions or need help, open an issue on GitHub.

---
