# ProductsApp 📦

A fullstack product management application built with a Rails 7 API backend and a React frontend.

---

## 📌 About

**ProductsApp** demonstrates a decoupled fullstack architecture with a Rails API serving JSON endpoints consumed by a React client. The backend handles data persistence and business logic while the frontend manages the user interface independently.

Built as a personal project to practice fullstack development with a Rails API + React stack, CORS configuration, and seed data generation.

---

## 🖥️ Features

- Product listing and management
- RESTful JSON API built with Rails
- Decoupled React frontend consuming the API
- Cross-origin requests handled with rack-cors
- Seed data generated with Faker

---

## 🛠️ Tech Stack

### Backend
| | Technology |
|---|---|
| Language | Ruby 3.1.2 |
| Framework | Ruby on Rails 7.1.5 (API mode) |
| Database | PostgreSQL |
| CORS | rack-cors |
| Seed data | Faker |
| Server | Puma |

### Frontend
| | Technology |
|---|---|
| Framework | React |
| Location | `/client` directory |

---

## ⚙️ Getting started

### Prerequisites

- Ruby 3.1.2
- Rails 7.1.5
- PostgreSQL
- Node.js & npm
- Bundler

### Backend setup

```bash
# Clone the repository
git clone https://github.com/digidweb/productsApp.git
cd productsApp

# Install Ruby dependencies
bundle install

# Set up the database
rails db:create db:migrate db:seed

# Start the Rails API server (runs on port 3001)
rails server -p 3001
```

### Frontend setup

```bash
# Navigate to the client directory
cd client

# Install JavaScript dependencies
npm install

# Start the React development server (runs on port 3000)
npm start
```

Open your browser at `http://localhost:3000`

The React app will communicate with the Rails API at `http://localhost:3001`

---

## 🐳 Running with Docker

```bash
docker build -t productsapp .
docker run -p 3001:3001 productsapp
```

---

## 📁 Project structure

```
productsApp/
├── app/
│   ├── controllers/    # API controllers (JSON responses)
│   └── models/         # ActiveRecord models
├── client/             # React frontend application
│   ├── src/
│   │   ├── components/ # React components
│   │   └── App.js      # Main React entry point
├── config/
│   └── routes.rb       # API routes
├── db/
│   ├── migrate/        # Database migrations
│   └── seeds.rb        # Seed data with Faker
└── Gemfile             # Ruby dependencies
```

