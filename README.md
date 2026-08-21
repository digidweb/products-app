# Products App 📦

> An app for product management

Products App is a full-stack application that demonstrates how an independent React frontend can communicate with a Ruby on Rails backend through RESTful JSON API.

The project focus on full-stack integration between a Rails API backend and a modern JavaScript frontend, including **API design, database persistence, CORS configuration, and client-side application development**.

## ✨ Features

* 📦 Product creation, listing, updating, and deletion
* 🔌 RESTful JSON API
* 🔢 Versioned API under /api/v1
* ⚛️ Decoupled React frontend
* 🔄 React ↔ Rails API integration
* 🗄️ PostgreSQL persistence
* 🌐 CORS configuration
* 🧭 Client-side routing with React Router
* ⚡ Vite development environment
* 🌱 Development data generation with Faker
* 🐳 Docker support

## 🛠️ Tech Stack

### Backend

* Ruby
* Ruby on Rails
* Rails API mode
* Active Record

### Frontend

* React 18
* JavaScript
* Vite
* Axios
* React Router

### Databaseability to work

* PostgreSQL

### Development & Infrastructure

* rack-cors
* Faker
* Puma
* Docker

## 🏗️ Architecture

ProductsApp uses a **decoupled frontend/backend architecture**.

The React application is responsible for the user interface and communicates with the Rails application through HTTP requests.

```text
┌─────────────────────┐
│                     │
│   React Frontend    |
|                     |
|    React + Vite     |
|        Axios        |
|     React Router    │
│                     |
|   localhost:3000    │
│                     │
└──────────┬──────────┘
           │
           │ HTTP / JSON
           │
           ▼
┌─────────────────────┐
│                     │
│      Rails API      │
│                     |
|       /api/v1       |
|     Controllers     |
|                     |
|    localhost:3001   │
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

This separation allows the frontend and backend to evolve independently while communicating through a clearly defined API boundary.

## 🧠 Technical Highlights
### REST API & Versioning

The Rails backend exposes product resources through RESTful endpoints under:

```text
/api/v1/products
```

API versioning provides a clear boundary for future changes without coupling the frontend directly to an unversioned API.

Frontend / Backend Integration

The React frontend consumes the Rails API through HTTP requests using Axios

```text
React component
      ↓
Axios requestability to work
      ↓
  Rails API
      ↓
Active Record
      ↓
 PostgreSQL
      ↓
JSON response
      ↓
  React UI
    CORS
```

Because the frontend and backend run as independent applications during development, the Rails API is configured with rack-cors to allow cross-origin communication.

### Database Persistence

Products are persisted in PostgreSQL through Rails Active Record, with database changes managed through Rails migrations.

## 🔌 API

The main product endpoints follow standard REST conventions:

```text
Method     Endpoint                Purpose
GET        /api/v1/products        List products
GET        /api/v1/products/:id    Retrieve a product
POST       /api/v1/products        Create a product
PATCH      /api/v1/products/:id    Update a product
PUT        /api/v1/products/:id    Update a product
DELETE     /api/v1/products/:id    Delete a product
```

Example request:

```text
POST /api/v1/products
Content-Type: application/json
```
```json
{
  "product": {
    "name": "Wireless Headphones",
    "price": 199.90,
    "stock_quantity": 25,
    "description": "Bluetooth wireless headphones"
  }
}
```

The API returns JSON responses and uses HTTP status codes to communicate successful operations and validation failures.

## 🧪 Testing

Automated testing is an important next step for the project.

The backend can be extended with RSpec request/model tests, while the React application can use a dedicated JavaScript testing framework for component and integration tests.

Example backend test command:
```text
bundle exec rspec
```

## 🚀 Getting Started

### Prerequisites

Make sure you have installed:

* Ruby 3.1.2
* Rails 7.1.5
* PostgreSQL
* Node.js
* npm
* Bundler

Or run with Docker in a containerized environment.

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

The Rails API will be available at:

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
npm run devability to work
```

Vite will display the frontend development URL in the terminal.

The React application will communicate with the Rails API running on port `3001`.

## 🐳 Running with Docker

The project also includes Docker support.

### 1.Build the Docker image:

```bash
docker build -t productsapp .
```

### 2. Run the container:

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

## 🔮 Potential Improvements

If continuing the project, the following improvements would be natural next steps:

* Add automated request and model tests with RSpec
* Add React component and integration tests
* Add standardized API error responses
* Add authentication and authorization
* Add product search and filtering
* Add API documentation with OpenAPI/Swagger
* Add GitHub Actions for CI
* Add production deployment

## 📌 Portfolio Context

ProductsApp is part of a portfolio focused on Ruby on Rails backend and full-stack development.

The project complements Rails-focused applications by demonstrating practical experience with:

**Ruby on Rails · REST APIs · PostgreSQL · React · JavaScript · Axios · Vite · Docker**

The project demonstrates ability to work with a different architecture from a traditional Rails application: instead of rendering the frontend through Rails views, the Rails application exposes a JSON API consumed by an independent React client.
