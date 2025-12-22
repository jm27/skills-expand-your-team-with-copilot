# Mergington High School Activities Management System

A modern web application for managing extracurricular activities at Mergington High School. This system allows students to view and sign up for activities while providing teachers with tools to manage their programs.

## 📋 Project Overview

This is a full-stack web application built with:
- **Backend**: FastAPI (Python) - Modern, fast web framework
- **Database**: MongoDB - Flexible document storage
- **Frontend**: Vanilla HTML, CSS, JavaScript - Simple and responsive
- **Security**: Argon2 password hashing for teacher authentication

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- MongoDB (local or remote instance)
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/jm27/skills-expand-your-team-with-copilot.git
   cd skills-expand-your-team-with-copilot
   ```

2. **Install dependencies**
   ```bash
   pip install -r src/requirements.txt
   ```

3. **Run the application**
   ```bash
   python -m uvicorn src.app:app --host 0.0.0.0 --port 8000
   ```

4. **Access the application**
   - Main website: http://localhost:8000
   - API documentation: http://localhost:8000/docs
   - Alternative docs: http://localhost:8000/redoc

## 📚 Documentation

- **[Development Guide](docs/how-to-develop.md)** - Detailed setup and development instructions
- **[Changelog](CHANGELOG.md)** - All notable changes to the project
- **[Source Code README](src/README.md)** - Application-specific details

## ✨ Features

### For Students
- 📋 Browse all available extracurricular activities
- ✅ Sign up for activities with your school email
- 📅 View activity schedules and capacity
- ℹ️ See detailed descriptions for each activity

### For Teachers
- 🔐 Secure authentication system
- 👥 Manage activity participants
- 📊 Track enrollment and capacity

### Available Activities
- Chess Club
- Programming Class
- Morning Fitness
- Soccer Team
- Basketball Team
- Art Club
- Drama Club
- Math Club
- Debate Team
- Weekend Robotics Workshop
- Science Olympiad
- Sunday Chess Tournament

## 🛠️ Technology Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| Web Framework | FastAPI | Modern Python API framework with automatic docs |
| Server | Uvicorn | Lightning-fast ASGI server |
| Database | MongoDB | Flexible NoSQL database |
| Database Driver | PyMongo | Python MongoDB client |
| Password Security | Argon2 | Secure password hashing algorithm |
| Frontend | HTML/CSS/JS | Responsive web interface |

## 🔒 Security Features

- Argon2 password hashing for teacher accounts
- Email validation for student signups
- Secure authentication endpoints
- Input validation and sanitization

## 📖 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Redirect to main website |
| GET | `/activities` | Get all activities with details |
| POST | `/activities/{activity_name}/signup` | Sign up for an activity |
| GET | `/docs` | Interactive API documentation |

## 🧪 Development

### Using GitHub Codespaces

This project is optimized for GitHub Codespaces:

1. Open the repository in Codespaces
2. Wait for the container to build
3. Dependencies will be automatically installed
4. Use VS Code's Run and Debug view (F5) to start the application

### Local Development

See the [Development Guide](docs/how-to-develop.md) for comprehensive instructions.

## 📝 Contributing

This project is part of the GitHub Skills exercise "Expand your team with Copilot coding agent." It demonstrates how GitHub Copilot can help manage and maintain codebases.

## 📄 License

&copy; 2025 GitHub &bull; [MIT License](https://gh.io/mit)

## 🎓 Learning Resources

This project is part of GitHub Skills exercises:
- **Who is this for**: Developers at any experience level looking to accelerate their code workflow
- **What you'll learn**: How to assign Copilot an issue, review Copilot's work, provide feedback, and work on multiple issues in parallel
- **Prerequisites**: 
  - GitHub Copilot subscription (Pro or higher)
  - [Introduction to GitHub](https://github.com/skills/introduction-to-github)
  - [Getting Started with GitHub Copilot](https://github.com/skills/getting-started-with-github-copilot)

### How to start this exercise

[![Copy Exercise](https://img.shields.io/badge/Copy%20Exercise-%E2%86%92-1f883d?style=for-the-badge&logo=github&labelColor=197935)](https://github.com/new?template_owner=skills&template_name=expand-your-team-with-copilot&owner=%40me&name=skills-expand-your-team-with-copilot&description=Exercise:+Expand+your+team+with+GitHub+Copilot+coding+agent&visibility=public)

---

## 📞 Support

<details>
<summary>Having trouble? 🤷</summary><br/>

When copying the exercise, we recommend the following settings:

- For owner, choose your personal account or an organization to host the repository
- We recommend creating a public repository, since private repositories will use Actions minutes

If the exercise isn't ready in 20 seconds, please check the [Actions](../../actions) tab.

</details>

---

**[Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md)** | **[View Changelog](CHANGELOG.md)**
