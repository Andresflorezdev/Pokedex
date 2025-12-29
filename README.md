<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

# Pokedex API - NestJS Learning Project

This project is a RESTful Pokémon API developed as part of a **NestJS course**. It implements complete CRUD operations, validations, error handling, MongoDB integration, and Docker deployment following the course teachings.

## 📋 Description

Backend API inspired by Pokémon data structure, built by following a NestJS course and implementing best practices. The project includes:

- ✅ Complete Pokémon CRUD operations
- ✅ Validations with class-validator and class-transformer
- ✅ MongoDB integration using Mongoose
- ✅ Seed module to load initial data from PokeAPI
- ✅ Environment variables with validation
- ✅ Dockerization for development and production
- ✅ Pagination and filters
- ✅ Global error handling

## 🚀 Tech Stack

- **Framework**: NestJS
- **Database**: MongoDB
- **ODM**: Mongoose
- **Language**: TypeScript
- **Validation**: class-validator, class-transformer, Joi
- **HTTP Client**: Axios
- **Containers**: Docker & Docker Compose

## 📦 Installation and Setup

### Prerequisites

- Node.js (v18 or higher)
- Yarn or npm
- Docker and Docker Compose
- NestJS CLI (optional but recommended)

### Steps to run in development

1. **Clone the repository**
```bash
git clone https://github.com/Andresflorezdev/Pokedex.git
cd Pokedex
```

2. **Install dependencies**
```bash
yarn install
```

3. **Install Nest CLI globally** (if you don't have it)
```bash
npm i -g @nestjs/cli
```

4. **Start the database with Docker**
```bash
docker-compose up -d
```

5. **Configure environment variables**

Clone the `.env.template` file and rename it to `.env`:
```bash
cp .env.template . env
```

Fill in the environment variables defined in the `.env` file

6. **Run the application in development mode**
```bash
yarn start:dev
```

7. **Seed the database with initial data**

Make a GET request to the seed endpoint:
```bash
curl http://localhost:3000/api/v2/seed
```

Or visit in your browser: [http://localhost:3000/api/v2/seed](http://localhost:3000/api/v2/seed)

## 🐳 Docker Deployment

### Production Build

1. **Create environment file for production**
```bash
cp .env.template .env.prod
```

2. **Fill in the production environment variables**

3. **Build and start the production image**
```bash
docker-compose -f docker-compose.prod.yaml --env-file .env.prod up --build
```

## 📁 Project Structure

```
src/
├── common/          # Shared pipes, guards, interceptors
├── config/          # Environment variables configuration
├── pokemon/         # Main Pokémon module (CRUD)
└── seed/            # Module to populate the database
```

## 🔧 Available Scripts

```bash
# Development
yarn start:dev       # Development mode with hot-reload
yarn start:debug     # Debug mode

# Production
yarn build           # Build project
yarn start:prod      # Run compiled version

# Testing
yarn test            # Unit tests
yarn test:e2e        # End-to-end tests
yarn test: cov        # Test coverage

# Code Quality
yarn lint            # Lint and auto-fix
yarn format          # Format code with Prettier
```

## 🌐 API Endpoints

The API exposes the following main endpoints:

- `GET /api/v2/pokemon` - Get all Pokémon (with pagination)
- `GET /api/v2/pokemon/: id` - Get a Pokémon by ID
- `POST /api/v2/pokemon` - Create a new Pokémon
- `PATCH /api/v2/pokemon/:id` - Update a Pokémon
- `DELETE /api/v2/pokemon/:id` - Delete a Pokémon
- `GET /api/v2/seed` - Populate the database with initial data

## 📚 Learning Outcomes from the NestJS Course

This project was developed as part of a NestJS course, where I learned and applied concepts such as:

- NestJS modular architecture
- Decorators and dependency injection
- DTOs (Data Transfer Objects) and validation
- NoSQL database integration
- Custom exception handling
- Environment variables and configuration
- Validation and transformation pipes
- NestJS application dockerization
- Mongoose schemas and models
- External API consumption
- Backend design patterns
- RESTful API best practices

> **Note**: This repository contains the practical implementation of concepts learned during the NestJS course, specifically focused on building a Pokémon-like API similar to the official PokéAPI.

## 🔐 Environment Variables

The `.env.template` file contains the following variables:

```env
MONGODB=mongodb://localhost:27017/nest-pokemon
PORT=3000
DEFAULT_LIMIT=7
```

## 📝 Additional Notes

### Heroku redeploy without changes
```bash
git commit --allow-empty -m "Trigger Heroku deploy"
git push heroku main
```

⭐ If this project was helpful to you, don't forget to give it a star! 
