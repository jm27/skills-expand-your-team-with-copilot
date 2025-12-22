# Changelog

All notable changes to the Mergington High School Activities project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Initial project setup with FastAPI backend
- MongoDB database integration for activities and teacher accounts
- Student activity signup functionality
- Teacher authentication system with Argon2 password hashing
- Static frontend with HTML, CSS, and JavaScript
- Interactive API documentation via FastAPI
- Development guide with setup instructions

### Features
- View all available extracurricular activities
- Sign up for activities with email validation
- Activity capacity management (max participants)
- Multiple activities across weekdays and weekends
- RESTful API endpoints for activity management
- Teacher authentication endpoints

### Technical
- FastAPI web framework for modern Python API development
- Uvicorn ASGI server for running the application
- PyMongo for MongoDB database operations
- Argon2 for secure password hashing
- Static file serving for frontend assets

### Documentation
- README.md with project overview and getting started guide
- Development guide (docs/how-to-develop.md) with setup instructions
- API endpoint documentation via FastAPI automatic docs
- In-code documentation and docstrings

### Infrastructure
- GitHub Codespaces configuration for development environment
- VS Code launch configurations for debugging
- Requirements.txt for Python dependency management

## [Initial Release] - 2025-12-22

### Added
- Initial commit of Mergington High School Activities project
- Basic project structure and configuration files
- Sample data for 12 extracurricular activities
- Initial teacher accounts (Ms. Rodriguez, Mr. Chen, Principal Martinez)

---

## How to Update This Changelog

This changelog should be updated by GitHub Copilot whenever significant changes are made to the project. Changes should be categorized under:

- **Added** for new features
- **Changed** for changes in existing functionality
- **Deprecated** for soon-to-be removed features
- **Removed** for now removed features
- **Fixed** for any bug fixes
- **Security** for vulnerability fixes

Each version should have a date in YYYY-MM-DD format.
