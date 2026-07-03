# Social Media Backend API

A RESTful backend API for a social media application, built with Node.js, Express, and MongoDB. Supports user registration, JWT-based authentication, and full CRUD operations on posts. Containerized with Docker and deployed live on Render, with data persisted on MongoDB Atlas.

**Live Demo:** https://socialmediaapp-sqvv.onrender.com
*(Note: hosted on a free tier — the app may take 30-60 seconds to wake up if it's been inactive.)*

## Features

- User registration and login with hashed session-based JWT authentication
- Protected routes using custom authentication middleware
- Full CRUD support for posts (create, read, update, delete), scoped per authenticated user
- MongoDB + Mongoose for data modeling and persistence
- Dockerized for consistent local development and cloud deployment
- Deployed on Render with MongoDB Atlas as the cloud database

## Tech Stack

| Layer          | Technology              |
|----------------|--------------------------|
| Runtime        | Node.js                 |
| Framework      | Express.js               |
| Database       | MongoDB (Atlas)          |
| ODM            | Mongoose                 |
| Auth           | JSON Web Tokens (JWT) + express-session |
| Containerization | Docker                 |
| Hosting        | Render                   |

## API Endpoints

| Method | Endpoint         | Description                          | Auth Required |
|--------|------------------|---------------------------------------|----------------|
| GET    | `/`              | Serve homepage                        | No             |
| GET    | `/register`      | Serve registration page               | No             |
| GET    | `/login`         | Serve login page                      | No             |
| POST   | `/register`      | Register a new user                   | No             |
| POST   | `/login`         | Log in an existing user               | No             |
| GET    | `/post`          | Serve post creation page              | Yes            |
| POST   | `/post`          | Create a new post                     | Yes            |
| GET    | `/posts`         | Get all posts for the logged-in user  | Yes            |
| PUT    | `/posts/:postId` | Update a specific post                | Yes            |
| DELETE | `/posts/:postId` | Delete a specific post                | Yes            |
| GET    | `/logout`        | Log out and destroy session           | No             |

## Getting Started Locally

### Prerequisites
- Node.js installed
- Docker Desktop installed
- A MongoDB Atlas account (free tier works) or local MongoDB instance

### 1. Clone the repository
```bash
git clone https://github.com/magupillipooja-oss/rofgy-backend-nodejs-finalproject.git
cd rofgy-backend-nodejs-finalproject
```

### 2. Set up environment variables
Create a `.env` file in the project root:
```
MONGO_URI=your_mongodb_connection_string
```

### 3. Run with Docker
```bash
docker build . -t socialapp
docker run -p 3000:3000 --env-file .env socialapp
```

Or run locally without Docker:
```bash
npm install
node app.js
```

The app will be available at `http://localhost:3000`.

## Deployment

This project is deployed on [Render](https://render.com) using its native Docker support, with MongoDB Atlas as the cloud-hosted database. Environment variables (including the database connection string) are managed securely through Render's dashboard rather than committed to source control.

## Project Background

This project was built as part of the IBM Full-Stack JavaScript Developer Specialization capstone, extending the base coursework with production-oriented additions: environment-based configuration, Docker containerization, cloud database migration (MongoDB Atlas), and live deployment.

## Author

**Pooja**
GitHub: [@magupillipooja-oss](https://github.com/magupillipooja-oss)
