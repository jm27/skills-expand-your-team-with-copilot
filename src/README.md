# Mergington High School Activities - Application Source

A modern FastAPI-based web application that allows students to view and sign up for extracurricular activities at Mergington High School.

## 📂 Project Structure

```
src/
├── app.py                  # Main FastAPI application entry point
├── requirements.txt        # Python dependencies
├── backend/
│   ├── __init__.py
│   ├── database.py        # MongoDB configuration and data models
│   └── routers/           # API route handlers
│       ├── __init__.py
│       ├── activities.py  # Activity management endpoints
│       └── auth.py        # Authentication endpoints
└── static/                # Frontend assets
    ├── index.html         # Main web page
    ├── styles.css         # Styling
    └── app.js             # Client-side JavaScript
```

## ✨ Features

### Student Features
- 📋 **Activity Browser**: View all available extracurricular activities with details
- ✅ **Easy Signup**: Sign up for activities using your Mergington email address
- 📅 **Schedule Information**: See when activities meet (days and times)
- 👥 **Capacity Tracking**: View current enrollment vs. maximum capacity
- ℹ️ **Detailed Descriptions**: Learn about each activity before signing up

### Teacher Features
- 🔐 **Secure Login**: Authentication system with Argon2 password hashing
- 👥 **Participant Management**: View and manage activity enrollments
- 📊 **Activity Overview**: Track all activities and their status

### Technical Features
- 🚀 **Fast API**: Built with FastAPI for high performance
- 📝 **Auto Documentation**: Interactive API docs at `/docs` endpoint
- 💾 **MongoDB Storage**: Flexible NoSQL database for data persistence
- 🔒 **Security**: Argon2 password hashing and input validation
- 📱 **Responsive Design**: Works on desktop and mobile devices

## 🗄️ Database Schema

### Activities Collection
```json
{
  "_id": "Activity Name",
  "description": "Activity description",
  "schedule": "Human-readable schedule",
  "schedule_details": {
    "days": ["Monday", "Wednesday"],
    "start_time": "15:15",
    "end_time": "16:45"
  },
  "max_participants": 20,
  "participants": ["student1@mergington.edu", "student2@mergington.edu"]
}
```

### Teachers Collection
```json
{
  "_id": "username",
  "display_name": "Ms. Smith",
  "password": "hashed_password_with_argon2",
  "role": "teacher"
}
```

## 🛠️ API Endpoints

### Public Endpoints

#### Get All Activities
```http
GET /activities
```
Returns list of all activities with their details and current participant count.

**Response Example:**
```json
[
  {
    "name": "Chess Club",
    "description": "Learn strategies and compete in chess tournaments",
    "schedule": "Mondays and Fridays, 3:15 PM - 4:45 PM",
    "max_participants": 12,
    "current_participants": 2,
    "available_spots": 10
  }
]
```

#### Sign Up for Activity
```http
POST /activities/{activity_name}/signup?email=student@mergington.edu
```
Sign up a student for an activity.

**Parameters:**
- `activity_name` (path): Name of the activity
- `email` (query): Student's email address

**Response Example:**
```json
{
  "message": "Successfully signed up for Chess Club",
  "activity": "Chess Club",
  "email": "student@mergington.edu"
}
```

### Authentication Endpoints

#### Teacher Login
```http
POST /auth/login
```
Authenticate teacher account.

## 🔧 Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| fastapi | 0.115.12 | Web framework for building APIs |
| uvicorn | 0.34.2 | ASGI server for running FastAPI |
| pymongo | 4.12.1 | MongoDB Python driver |
| argon2 | 0.1.10 | Password hashing library |
| argon2-cffi | 23.1.0 | Argon2 CFFI bindings |

## 🚀 Running the Application

### Basic Usage
```bash
# Install dependencies
pip install -r requirements.txt

# Run the application
python -m uvicorn src.app:app --host 0.0.0.0 --port 8000
```

### Development Mode (with auto-reload)
```bash
python -m uvicorn src.app:app --reload --host 0.0.0.0 --port 8000
```

### Access Points
- **Main Website**: http://localhost:8000
- **API Documentation**: http://localhost:8000/docs
- **Alternative Docs**: http://localhost:8000/redoc

## 🧪 Development

### Debugging with VS Code

1. Open VS Code's Run and Debug view (Ctrl+Shift+D)
2. Select "Launch Mergington WebApp" configuration
3. Press F5 or click the green play button
4. The application will start with the debugger attached

### Hot Reload

FastAPI's auto-reload feature automatically restarts the server when code changes are detected. This is enabled by default in development mode.

### Testing Endpoints

Use the interactive API documentation at http://localhost:8000/docs to:
- View all available endpoints
- Test API calls directly from the browser
- See request/response schemas
- Execute test requests

## 💾 Data Storage

> **⚠️ Important**: All data is stored in MongoDB. Make sure you have a MongoDB instance running on `mongodb://localhost:27017/` or update the connection string in `backend/database.py`.

### Initial Data

The application automatically initializes with:
- **12 extracurricular activities** (Chess Club, Programming Class, etc.)
- **3 teacher accounts** (Ms. Rodriguez, Mr. Chen, Principal Martinez)
- **Sample student enrollments** in various activities

### Database Initialization

On startup, the application:
1. Connects to MongoDB
2. Checks if collections are empty
3. Inserts initial data if needed
4. Ready to serve requests

## 🔒 Security Considerations

- **Password Hashing**: Teacher passwords are hashed using Argon2, a secure password hashing algorithm
- **Email Validation**: Student emails are validated to ensure they are in the correct format
- **Input Sanitization**: All inputs are validated to prevent injection attacks
- **MongoDB Security**: Ensure MongoDB authentication is enabled in production

## 📚 Additional Resources

- **[Main README](../README.md)** - Project overview and quick start
- **[Development Guide](../docs/how-to-develop.md)** - Detailed setup instructions
- **[Changelog](../CHANGELOG.md)** - Version history and changes
- **[FastAPI Documentation](https://fastapi.tiangolo.com/)** - FastAPI framework docs
- **[MongoDB Documentation](https://www.mongodb.com/docs/)** - MongoDB database docs

## 🤝 Contributing

This project is maintained by GitHub Copilot as part of the GitHub Skills exercise. Changes should be managed through GitHub issues and pull requests, allowing Copilot to assist with code modifications.

## 📝 Notes

- The application uses MongoDB for persistent storage, so data is maintained between server restarts
- All activity schedules support weekday and weekend meetings
- Student emails must be from the @mergington.edu domain
- Each activity has a maximum capacity that cannot be exceeded
