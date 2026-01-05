# Flask-Server Social Media API

A hybrid Flask/FastAPI backend application for a social media platform with user management, authentication, and social features like following/followers system.

## 🚀 Features

- **User Authentication**: Sign up and sign in functionality
- **User Profiles**: Complete user profile management with bio and avatar
- **Social Features**: Follow/unfollow users with followers and following lists
- **User Management**: Update and delete user accounts
- **MongoDB Integration**: Persistent data storage
- **CORS Support**: Cross-origin resource sharing enabled
- **Dual Framework**: Both Flask and FastAPI implementations

## 📁 Project Structure

```
flask-server/
├── config/
│   └── db.py              # Database connection configuration
├── models/
│   └── user.py            # Pydantic models for request validation
├── routes/
│   └── user.py            # FastAPI route handlers
├── schemas/
│   └── user.py            # Data serialization schemas
├── server.py              # Flask application (alternative implementation)
├── index.py               # FastAPI application (main)
├── package.json           # Node.js dependencies (for additional tools)
└── .gitignore            # Git ignore rules
```

## 🛠️ Tech Stack

- **Backend Frameworks**: Flask, FastAPI
- **Database**: MongoDB
- **ODM**: PyMongo
- **Validation**: Pydantic
- **CORS**: Flask-CORS, FastAPI CORS middleware
- **Authentication**: UUID-based tokens

## 📋 Prerequisites

- Python 3.7+
- MongoDB (running locally on port 27017)
- pip (Python package manager)

## ⚡ Quick Start

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd flask-server
```

### 2. Install Python dependencies
```bash
pip install flask fastapi uvicorn pymongo flask-cors pydantic bson
```

### 3. Start MongoDB
Make sure MongoDB is running on `localhost:27017`

### 4. Run the application

**Option A: FastAPI (Recommended)**
```bash
cd flask-server
uvicorn index:app --reload
```

**Option B: Flask**
```bash
cd flask-server
python server.py
```

## 📚 API Endpoints

### Authentication
- `POST /signup` - Create new user account
- `POST /signin` - User login

### User Management
- `GET /allusers` - Get all users (excluding passwords)
- `GET /{id}` - Get user profile by ID
- `POST /update` - Update user profile
- `POST /userDelete` - Delete user account

### Social Features
- `POST /followingDetails` - Follow/unfollow users
- `GET /followingListById/{id}` - Get user's following list
- `GET /followerListById/{id}` - Get user's followers list


## 🗄️ Database Schema


### Production Setup
1. Use a production WSGI server like Gunicorn for Flask
2. Use Uvicorn with multiple workers for FastAPI
3. Set up proper MongoDB authentication
4. Configure environment-specific CORS settings
5. Implement proper logging
