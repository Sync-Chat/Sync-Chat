# MERN Real-Time Application 

## 📌 Project Description

This is a **full-stack MERN application** that supports **real-time features using Socket.IO**, **secure authentication using Clerk**, and **profile image uploads using Cloudinary**.

The project follows a **client–server architecture** where:

* The **frontend (React + Vite)** handles UI, authentication flow, and socket connections
* The **backend (Node + Express)** manages APIs, database operations, socket events, and media handling
* **MongoDB** is used for persistent data storage

---

## ⚙️ How the Project Works (Core Flow)

### 1. Authentication (Clerk)

* Users sign up or log in using **Clerk** on the frontend
* Clerk manages sessions and user identity
* The frontend sends authenticated requests to the backend
* The backend verifies users using `CLERK_SECRET_KEY`

### 2. Backend & Database

* Express exposes REST APIs for application logic
* MongoDB stores user-related data and application records
* Mongoose is used for schema and data modeling

### 3. Real-Time Communication (Socket.IO)

* Socket.IO is initialized on the backend server (`PORT 4000`)
* When the frontend loads, it establishes a socket connection
* Events are emitted and listened to for real-time updates
* Both HTTP APIs and WebSocket connections run on the same server

### 4. Profile Image Upload (Cloudinary)

* Users upload profile images from the frontend
* Images are sent to the backend
* The backend uploads files to **Cloudinary**
* Cloudinary returns a secure image URL
* That URL is stored in MongoDB and used across the app

---

## 🧠 Tech Stack

**Frontend**

* React (Vite)
* Clerk Authentication
* Socket.IO Client

**Backend**

* Node.js
* Express.js
* MongoDB + Mongoose
* Socket.IO
* Cloudinary
* Clerk Server SDK

---

## 📂 Project Structure

```
root/
│
├── client/          # Frontend (React + Vite)
│   ├── src/
│   ├── .env
│   └── package.json
│
├── server/          # Backend (Node + Express)
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   ├── socket/
│   ├── .env
│   └── package.json
│
└── README.md
```

---

## 🔐 Environment Variables

### Server (`server/.env`)

```
PORT=4000
MONGO_URL=

CLERK_SECRET_KEY=

CLOUD_NAME=
CLOUD_API_KEY=
CLOUD_API_SECRET=
```

### Client (`client/.env`)

```
VITE_CLERK_PUBLISHABLE_KEY=
```

## 🚀 Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone <repository-url>
cd <project-folder>
```

---

### 2️⃣ Backend Setup

```bash
cd server
npm install
```

Create a `.env` file inside `server` and add the required variables.

Start the backend:

```bash
npm run dev
```

Server runs on:

```
http://localhost:4000
```

---

### 3️⃣ Frontend Setup

```bash
cd client
npm install
```

Create a `.env` file inside `client`:

```
VITE_CLERK_PUBLISHABLE_KEY=
```

Start the frontend:

```bash
npm run dev
```

Frontend runs on:

```
http://localhost:5173
```

---

## 🔌 Socket.IO Notes

* Socket.IO runs on **PORT 4000**
* Frontend connects directly to the backend server
* Backend must be running before frontend socket connection starts

---

