# 🚨 Crime Analytics & Public Safety Platform

A full-stack crime analytics and public safety platform that enables secure crime reporting, missing person management, police notices, real-time location sharing, and machine-learning–based crime prediction.

This system is designed to bridge the gap between the public and law enforcement while maintaining data integrity, moderation, and role-based access control.

---

## 🧩 Key Features

### 👥 Role-Based Access
- **Public Users**
  - Register and log in securely
  - Submit crime tips
  - Report missing persons with photo uploads
  - Track tip status using Tip ID
  - View approved missing person cases
  - View public police notices
  - Use crime prediction feature

- **Officials (Admin / Analyst)**
  - Add verified crime records
  - Review and approve/reject missing person reports
  - Manage and update public crime tips
  - Post police notices (including *Most Wanted*)
  - Advanced crime search with filters
  - Access analytics and summaries
  - Receive real-time user location data

---

## 🧠 Machine Learning Integration

- Predicts crime occurrence based on:
  - State
  - District
  - Crime type
- Uses trained ML models stored as `.pkl` files
- Python (`prediction.py`) is invoked from Node.js using `child_process`
- Returns prediction results as JSON

---

## 🗂️ Project Structure

├── uploads/
│ ├── missing_photos/
│ └── wanted/
|
|── crime_model.pkl
|── crime_encoder.pkl
│── district_encoder.pkl
├── prediction.py
├── server.js
│── *.html
│── *.js
│── *.css
├── package.json
└── README.md


---

## 🔐 Authentication & Security

- JWT-based authentication
- Role-based authorization middleware
- Secure password hashing using bcrypt
- Protected routes for officials
- Public routes limited to verified data only
- Multer-based file upload handling

---

## 🧾 Core Modules

### 📌 Crime Reporting
- Public tips and official crime records are stored separately
- Prevents unverified data from polluting official crime datasets

### 🧍 Missing Person Management
- Public submissions → moderation queue
- Official approval → public visibility
- Photo evidence supported

### 📢 Police Notices
- Categories include General Notices and Most Wanted
- Image mandatory for high-priority alerts
- Posted only by authorized officials

### 📊 Crime Analytics
- Crime summaries
- Charts by crime type
- Geospatial crime mapping
- Advanced multi-filter crime search

### 📍 Real-Time Location Sharing
- Logged-in users can share GPS coordinates
- Stored and logged for police monitoring simulation

---

## 🛠️ Tech Stack

### Backend
- Node.js
- Express.js
- MySQL
- JWT Authentication
- Multer

### Machine Learning
- Python
- scikit-learn
- NumPy
- Pandas
- Joblib

### Frontend
- HTML
- CSS
- JavaScript

---

## 🚀 How to Run the Project

### 1️⃣ Install Dependencies
```bash
npm install
2️⃣ Start MySQL

Ensure MySQL is running and database tables are created.

3️⃣ Run the Server
node server.js


Server will run at:

http://localhost:3000


API Highlights

/api/signup – User registration

/api/login – User authentication

/api/crimes – Crime reporting (role-based)

/api/missing/report – Missing person reporting

/api/missing/public-view – Public verified cases

/api/notices/all – Public police notices

/api/tips/:id/status – Tip status tracking

/predict – Crime prediction (ML)


🎓 Academic Relevance

This project demonstrates:

Full-stack system design

Secure authentication and authorization

Moderation pipelines

ML integration with backend services

Real-world public safety application

📜 License

This project is for academic and educational purposes.
# Crime_Data_Analysis_Using_Machine_Learning
