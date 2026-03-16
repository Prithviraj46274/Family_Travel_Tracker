# 🌍 Family Travel Tracker

A **Node.js + Express + PostgreSQL** web application that allows users to track the countries they have visited.
Users can create profiles and add countries they have traveled to, and the app keeps track of the total number of visited countries.

---

## 🚀 Features

* Add countries you have visited
* Track the total number of visited countries
* Multiple user profiles
* Color-coded users
* Data stored in PostgreSQL database
* Server-side rendering using EJS

---

## 🛠️ Tech Stack

* Node.js
* Express.js
* PostgreSQL
* EJS
* Body Parser

---

## 📂 Project Structure

```
Family-Travel-Tracker
│
├── public/            # Static files (CSS, images)
├── views/             # EJS templates
│   ├── index.ejs
│   └── new.ejs
│
├── index.js           # Main server file
├── package.json
└── README.md
```

---

## ⚙️ Prerequisites

Before running this project, install the following:

1. **Node.js**
2. **PostgreSQL**

Download PostgreSQL:
https://www.postgresql.org/download/

---

## 🗄️ Database Setup

Open PostgreSQL and create a database.

```sql
CREATE DATABASE world_travel;
```

Create the required tables:

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50),
  color VARCHAR(50)
);

CREATE TABLE countries (
  id SERIAL PRIMARY KEY,
  country_name VARCHAR(100),
  country_code VARCHAR(10)
);

CREATE TABLE visited_countries (
  id SERIAL PRIMARY KEY,
  country_code VARCHAR(10),
  user_id INTEGER REFERENCES users(id)
);
```

---

## 🔑 Configure Database Connection

Open **index.js** and update the PostgreSQL login credentials:

```javascript
const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "world_travel",
  password: "your_password",
  port: 5432,
});
```

Make sure the credentials match your PostgreSQL installation.

---

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/world-travel-tracker.git
cd world-travel-tracker
```

Install dependencies:

```bash
npm install
```

---

## ▶️ Run the Application

Start the server:

```bash
node index.js
```

Open your browser and visit:

```
http://localhost:3000
```

---

## 📸 How It Works

1. Select or create a user profile.
2. Enter the name of a country.
3. The application finds the country code from the database.
4. The country is added to the list of visited countries for that user.

---

## 🧠 Learning Goals

This project demonstrates:

* Express server setup
* PostgreSQL database integration
* SQL queries with Node.js
* Handling multiple users
* Server-side rendering with EJS

---

