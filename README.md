# Products App 📦

> A full-stack product management application built with a decoupled Ruby on Rails API and React frontend.

ProductsApp is a full-stack application that demonstrates how an independent React frontend can communicate with a Ruby on Rails API through RESTful JSON endpoints.

The project was built to practice the integration between a Rails API backend and a modern JavaScript frontend, including API design, database persistence, CORS configuration, and client-side application development.

## ✨ Features

* 📦 Product listing and management
* 🔌 RESTful JSON API built with Ruby on Rails
* ⚛️ Decoupled React frontend
* 🗄️ PostgreSQL persistence
* 🔄 Cross-origin communication between React and Rails
* 🌱 Seed data generation with Faker
* 🐳 Docker support
* 🏗️ Separate backend and frontend applications

## 🛠️ Tech Stack

### Backend

* **Ruby 3.1.2**
* **Ruby on Rails 7.1.5**
* **Rails API mode**
* **PostgreSQL**
* **Active Record**
* **rack-cors**
* **Faker**
* **Puma**

### Frontend

* **React**
* **JavaScript**
* **npm**

### Infrastructure

* **Docker**

## 🏗️ Architecture

ProductsApp uses a **decoupled frontend/backend architecture**.

The React application is responsible for the user interface and communicates with the Rails application through HTTP requests.

```text
┌─────────────────────┐
│                     │
│   React Frontend    │
│    localhost:3000   │
│                     │
└──────────┬──────────┘
           │
           │ HTTP / JSON
           │
           ▼
┌─────────────────────┐
│                     │
│    Rails API        │
│    localhost:3001   │
│                     │
└──────────┬──────────┘
           │
           │ Active Record
           │
           ▼
┌─────────────────────┐
│                     │
│     PostgreSQL      │
│                     │
└─────────────────────┘
```

This separation allows the frontend and backend to evolve independently while communicating through a defined API boundary.

## 🔌 API

The Rails backend exposes JSON endpoints consumed by the React application.

The API is responsible for:

* Receiving HTTP requests
* Validating and processing application data
* Persisting products in PostgreSQL
* Returning JSON responses to the frontend

CORS is configured with **rack-cors** to allow the React development server to communicate with the Rails API running on a different port.

## 📁 Project Structure

```text
productsApp/
├── app/
│   ├── controllers/       # API controllers and JSON responses
│   └── models/            # Active Record models
│
├── client/                # React frontend
│   └── src/
│       ├── components/    # React components
│       └── App.js         # Main React entry point
│
├── config/
│   └── routes.rb          # API routes
│
├── db/
│   ├── migrate/           # Database migrations
│   └── seeds.rb           # Seed data generation
│
├── Dockerfile
├── Gemfile
└── package.json
```

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

* Ruby 3.1.2
* Rails 7.1.5
* PostgreSQL
* Node.js
* npm
* Bundler

### 1. Clone the repository

```bash
git clone https://github.com/digidweb/products-app.git
cd products-app
```

### 2. Set up the Rails API

Install Ruby dependencies:

```bash
bundle install
```

Create and configure the database:

```bash
rails db:create
rails db:migrate
rails db:seed
```

Start the Rails API:

```bash
rails server -p 3001
```

The API will be available at:

```text
http://localhost:3001
```

### 3. Set up the React frontend

Open another terminal and navigate to the client:

```bash
cd client
```

Install JavaScript dependencies:

```bash
npm install
```

Start the React development server:

```bash
npm start
```

The frontend will be available at:

```text
http://localhost:3000
```

The React application will communicate with the Rails API running on port `3001`.

## 🐳 Running with Docker

The project also includes Docker support.

Build the Docker image:

```bash
docker build -t productsapp .
```

Run the container:

```bash
docker run -p 3001:3001 productsapp
```

> The local development workflow above is recommended when working on both the Rails API and React frontend independently.

## 🌱 Seed Data

The project uses **Faker** to generate sample product data.

To recreate the seed data:

```bash
rails db:seed
```

This makes it easier to populate the development database with realistic data while developing and testing the application.

## 🔄 Data Flow

A typical request follows this flow:

```text
User interaction
      ↓
React component
      ↓
HTTP request
      ↓
Rails API controller
      ↓
Active Record model
      ↓
PostgreSQL
      ↓
JSON response
      ↓
React UI update
```

This architecture provides practical experience with the complete lifecycle of a full-stack request, from user interaction to database persistence and back to the frontend.

## 💡 Technical Takeaways

The main goal of this project was to gain hands-on experience with the integration between a Rails backend and an independent React frontend.

Key areas explored include:

* Designing RESTful JSON endpoints
* Building a Rails API-only application
* Connecting React to a backend API
* Handling CORS between separate applications
* Persisting application data with PostgreSQL
* Managing database migrations
* Generating development data with Faker
* Structuring a React application with reusable components
* Containerizing the backend with Docker
* Separating frontend and backend responsibilities

## 🔮 Potential Improvements

If continuing the project, the following improvements would be natural next steps:

* Add automated tests for API endpoints and React components
* Add request validation and standardized API error responses
* Implement product creation, editing, and deletion through the React interface
* Add product search and filtering
* Add pagination to the API
* Add authentication and authorization
* Add API documentation with OpenAPI/Swagger
* Add GitHub Actions for automated testing and code quality checks
* Add production deployment for both frontend and backend
* Add a dedicated API versioning strategy

## 📄 Project Context

ProductsApp is a personal full-stack project focused on practicing the integration of **Ruby on Rails API** with **React**.

The project demonstrates a different architecture from a traditional Rails application: instead of rendering the frontend through Rails views, the Rails application exposes a JSON API consumed by an independent React client.

This architecture provides practical experience with the responsibilities and communication boundaries between a backend API and a JavaScript frontend.
