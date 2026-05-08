📋 Table of Contents

Overview
Features
Tech Stack
Project Structure
Getting Started
API Endpoints
Database Schema
Contributing

🎯 Overview

The Cinema Management System is a complete web solution that allows cinema administrators to manage their operations end-to-end — from programming showtimes and assigning auditoriums to handling reservations and ticket printing. Built with a Vue.js frontend and a Node.js/Express REST API connected to a PostgreSQL relational database.

✨ Features

ModuleDescription🎥 MoviesCreate, edit and delete movie listings with poster, synopsis and duration🕐 ShowtimesSchedule multiple functions per movie across different auditoriums🪑 Seat ReservationsInteractive seat map with real-time availability🎫 TicketsGenerate and manage ticket sales per reservation🏛️ AuditoriumsConfigure auditorium layouts and seat capacities👤 UsersBasic authentication and user management

🛠️ Tech Stack

Frontend

Vue.js 3 — Component-based UI framework
Bootstrap CSS — Responsive layout and styling
JavaScript (ES6+) — Application logic
HTML5 — Markup

Backend

Node.js — JavaScript runtime
Express.js — Web framework and routing
REST API — JSON-based communication

Database

PostgreSQL — Relational database
Raw SQL queries with structured schema design


📁 Project Structure

Proyecto-Cines-Final/
├── Front/                  # Vue.js frontend
│   ├── src/
│   │   ├── components/     # Reusable Vue components
│   │   ├── views/          # Page-level components
│   │   ├── router/         # Vue Router configuration
│   │   └── assets/         # Static assets
│   └── package.json
│
├── backend/                # Node.js + Express API
│   ├── routes/             # API route definitions
│   ├── controllers/        # Business logic handlers
│   ├── db/                 # Database connection & queries
│   └── package.json
│
└── README.md

🚀 Getting Started

Prerequisites

Node.js v18+
PostgreSQL v14+
npm v9+

Installation

1. Clone the repository
bashgit clone https://github.com/LuisAOL2003/Proyecto-Cines-Final.git
cd Proyecto-Cines-Final
2. Set up the database
bash# Create the database in PostgreSQL
createdb cinema_db

# Run the schema (if provided)

psql -d cinema_db -f backend/db/schema.sql

3. Configure environment variables

Create a .env file inside the backend/ folder:
envDB_HOST=localhost
DB_PORT=5432
DB_NAME=cinema_db
DB_USER=your_db_user
DB_PASS=your_db_password
PORT=3000

4. Start the backend
bashcd backend
npm install
npm run dev
The API will be available at http://localhost:3000

5. Start the frontend
bashcd ../Front
npm install
npm run dev
The app will be available at http://localhost:5173

📡 API Endpoints

MethodEndpointDescriptionGET/api/moviesList all moviesPOST/api/moviesCreate a new moviePUT/api/movies/:idUpdate a movieDELETE/api/movies/:idDelete a movieGET/api/showtimesList all showtimesPOST/api/showtimesCreate a showtimeGET/api/reservationsList all reservationsPOST/api/reservationsCreate a reservationGET/api/auditoriumsList all auditoriums

🗄️ Database Schema

The relational model includes the following core entities:
Movies ──< Showtimes ──< Reservations ──< Tickets
               │
           Auditoriums ──< Seats
           
Key relationships:

A Movie can have multiple Showtimes
Each Showtime is assigned to one Auditorium
A Reservation belongs to a Showtime and contains one or more Seats
Each Ticket corresponds to a confirmed Reservation

👤 Author
Luis Ojeda — Full Stack Developer

🌐 Portfolio: portafolio-luis-ojeda.vercel.app
💼 LinkedIn: linkedin.com/in/luisojeda-93871729b
🐙 GitHub: @LuisAOL2003
📧 Email: luisojelopez@gmail.com


