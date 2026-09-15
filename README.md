# FoodieHub

FoodieHub is a full-stack online food ordering application built with React and Spring Boot. Users can create an account, log in, browse restaurants and menu items, add food to a shopping cart, and place an order through checkout.

## Features

* User registration and login
* Restaurant browsing
* Menu item display
* Add items to the shopping cart
* View cart items and total price
* Checkout and order placement
* PostgreSQL data persistence
* Docker-based local database setup

## Tech Stack

### Frontend

* React 18
* JavaScript
* Ant Design
* HTML
* CSS

### Backend

* Java 21
* Spring Boot 4.1
* Spring Web MVC
* Spring Security
* Spring Data JDBC
* PostgreSQL
* Caffeine Cache
* Gradle
* Docker

## Project Structure

```text
FoodieHub/
├── frontend/                  # React frontend application
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── App.js
│   │   └── utils.js
│   ├── package.json
│   └── package-lock.json
│
└── backend/                   # Spring Boot backend application
    ├── src/
    │   ├── main/
    │   │   ├── java/
    │   │   │   └── com/laioffer/onlineorder/
    │   │   │       ├── controller/
    │   │   │       ├── entity/
    │   │   │       ├── model/
    │   │   │       ├── repository/
    │   │   │       └── service/
    │   │   └── resources/
    │   └── test/
    ├── build.gradle
    ├── docker-compose.yml
    └── Dockerfile
```

## Getting Started

### Prerequisites

Make sure the following tools are installed:

* Node.js and npm
* Java 21
* Docker Desktop
* Git

## Run the Application Locally

### 1. Clone the Repository

```bash
git clone https://github.com/yx-w-yx/FoodieHub.git
cd FoodieHub
```

### 2. Start the PostgreSQL Database

Open a terminal in the project directory:

```bash
cd backend
docker compose up -d
```

The PostgreSQL database runs on port `5432`.

### 3. Start the Backend

The Docker configuration uses `secret` as the local database password. In PowerShell, run:

```powershell
$env:DATABASE_PASSWORD="secret"
.\gradlew bootRun
```

The backend runs at:

```text
http://localhost:8080
```

### 4. Start the Frontend

Open another terminal:

```bash
cd frontend
npm install
npm start
```

The frontend runs at:

```text
http://localhost:3000
```

The frontend development server forwards API requests to the backend at `http://localhost:8080`.

## Build the Application

### Build the Frontend

```bash
cd frontend
npm run build
```

### Build the Backend

On Windows:

```powershell
cd backend
.\gradlew build
```

The generated Spring Boot JAR file will be located in:

```text
backend/build/libs/
```

## Testing

Run the backend tests with:

```powershell
cd backend
.\gradlew test
```

Run the frontend tests with:

```bash
cd frontend
npm test
```

## Future Improvements

* Add order history
* Allow users to remove individual items from the shopping cart
* Add restaurant and menu management
* Improve authentication and authorization
* Expand automated test coverage
* Add continuous integration and deployment
