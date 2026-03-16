# Social Platform

A full-stack social media platform built with a Node.js/Express backend and a modern frontend framework, using MongoDB for data persistence and Cloudinary for media storage.

---

## Project Structure

```
social-platform/
├── BackEnd/        # Node.js + Express REST API
├── Front-End/      # Frontend application
└── package.json    # Root scripts for build & start
```

---

## Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [npm](https://www.npmjs.com/) v9+
- A [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) cluster (or local MongoDB instance)
- A [Cloudinary](https://cloudinary.com/) account

---

## Environment Variables

Create a `.env` file inside the `BackEnd/` directory with the following variables:

```dotenv
# MongoDB
MONGODB_URI=your_mongodb_connection_string

# Server
PORT=5001
NODE_ENV=development

# Authentication
JWT_SECRET=your_jwt_secret_key

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

> ⚠️ **Never commit the `.env` file to version control.** Make sure `.env` is listed in `.gitignore`.

### Variable Reference

| Variable | Description |
|---|---|
| `MONGODB_URI` | Full MongoDB connection string (e.g. from Atlas) |
| `PORT` | Port the backend server listens on |
| `NODE_ENV` | Runtime environment (`development` / `production`) |
| `JWT_SECRET` | Secret key used to sign and verify JWT tokens |
| `CLOUDINARY_CLOUD_NAME` | Your Cloudinary cloud name |
| `CLOUDINARY_API_KEY` | Your Cloudinary API key |
| `CLOUDINARY_API_SECRET` | Your Cloudinary API secret |

---

## Installation & Running

### Install & Build (from root)

```bash
npm run build
```

This command will:
1. Install dependencies in `BackEnd/`
2. Install dependencies in `Front-End/`
3. Build the `Front-End/` application

### Start the Backend Server (from root)

```bash
npm start
```

This starts the backend server on the port defined in your `.env` (`5001` by default).

---

## Scripts Summary

| Command | Description |
|---|---|
| `npm run build` | Installs deps for both BackEnd & Front-End, then builds Front-End |
| `npm start` | Starts the BackEnd server |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Node.js, Express |
| Database | MongoDB (Atlas) |
| Auth | JWT |
| Media Storage | Cloudinary |
| Frontend | (see `Front-End/` directory) |

---

## Notes

- Ensure your MongoDB Atlas cluster has the correct IP whitelist entries (or `0.0.0.0/0` for Docker deployments).
- The `JWT_SECRET` should be a long, random string in production. Use a secret manager or environment injection — never a plain text file.
- For production, set `NODE_ENV=production` and ensure the frontend build output is served statically by the backend.
