# Karshak Backend Guide

## Overview

The Karshak backend provides the application APIs used by the Farmer and Buyer workflows. It is built with Node.js and Express.js and stores application data in PostgreSQL through Prisma ORM.

## Backend Technologies

- Node.js
- Express.js
- REST APIs
- JWT authentication
- Prisma ORM
- PostgreSQL
- Neon PostgreSQL
- Cloudinary for product images

## Main Backend Responsibilities

The backend is responsible for:

- User registration and authentication
- Farmer and Buyer role-based workflows
- Protected API routes
- Product creation and retrieval
- Product categories
- User data
- Order creation and management
- Checkout-related server operations
- Database access through Prisma ORM
- Product image integration with Cloudinary

## API Areas

The project follows a REST-style backend architecture. Main API areas include:

```text
/api/auth
/api/products
/api/orders
/api/categories
/api/users
```

These areas support authentication and the main marketplace features of Karshak.

## Authentication and Authorization

Karshak uses JWT-based authentication. Protected backend routes require authenticated requests, and application behavior is separated for Farmer and Buyer roles.

## Database Layer

Karshak uses Prisma ORM to interact with PostgreSQL. The production database is hosted with Neon PostgreSQL.

Major application models include:

- User
- Farmer
- Buyer
- Category
- Product
- Order

## Image Storage

Product images are stored using Cloudinary. Cloudinary credentials must be stored as environment variables and must never be committed to GitHub.

## Running the Backend Locally

From the Karshak repository:

```bash
cd server
npm install
npm run dev
```

Depending on the configured package scripts, the backend can also be started with:

```bash
npm start
```

## Important Environment Variables

The backend uses environment variables such as:

```text
DATABASE_URL
JWT_SECRET
CLOUDINARY_CLOUD_NAME
CLOUDINARY_API_KEY
CLOUDINARY_API_SECRET
CLIENT_URL
```

Never place real production secrets in documentation or commit a `.env` file containing secrets.

## Production Backend

The production backend API is deployed on Vercel:

https://karshak-server.vercel.app/

---

This guide gives a high-level overview of the current Karshak backend without exposing any private credentials or production secrets.
