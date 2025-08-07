# Finance Manager Application

This repository contains a full-stack personal finance management application, consisting of a Spring Boot backend API and a React frontend. The application allows users to track income and expenses, manage financial planning, view analytics, and more.

## Table of Contents

-   [Features](#features)
-   [Technologies Used](#technologies-used)
-   [Project Structure](#project-structure)
-   [Setup and Installation](#setup-and-installation)
    -   [Prerequisites](#prerequisites)
    -   [Backend Setup](#backend-setup)
    -   [Frontend Setup](#frontend-setup)
-   [Usage](#usage)
-   [API Endpoints](#api-endpoints)
-   [Authentication](#authentication)
-   [Contributing](#contributing)
-   [License](#license)

## Features

The Finance Manager application provides the following key features:

**Backend (FinanceManager-API):**
-   User authentication and authorization (JWT-based).
-   User registration and login.
-   Management of financial transactions (income, expenses).
-   Financial planning functionalities.
-   Analytics and reporting for financial data.
-   Data persistence using PostgreSQL.

**Frontend (FinanceManager-React):**
-   User-friendly dashboard for an overview of finances.
-   Sections for managing income and expenses.
-   Financial planning interface.
-   Detailed analytics and reporting views.
-   User settings management.
-   Admin functionalities (if applicable).
-   Secure login and signup pages.

## Technologies Used

**Backend (FinanceManager-API):**
-   Java 17
-   Spring Boot (Web, Data JPA, Security)
-   PostgreSQL
-   JWT (JSON Web Tokens) for authentication
-   Lombok
-   Maven

**Frontend (FinanceManager-React):**
-   React 19
-   TypeScript
-   Vite
-   Axios for API communication
-   React Router DOM for navigation
-   Chart.js & Recharts for data visualization
-   Font Awesome for icons
-   ESLint for code quality

## Project Structure

The repository is organized into two main directories:

```
.
├── FinanceManager-API/          # Spring Boot Backend API
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/FinanceManagerAPI/FinanceManagerAPI/
│   │   │   │   ├── Authenticator/   # JWT utilities and user details service
│   │   │   │   ├── Configs/         # Security configurations
│   │   │   │   ├── Controller/      # REST API controllers (Finance, User)
│   │   │   │   ├── DTO/             # Data Transfer Objects
│   │   │   │   ├── Entities/        # JPA Entities and request/response models
│   │   │   │   ├── Repositories/    # Spring Data JPA repositories
│   │   │   │   └── Services/        # Business logic services
│   │   │   └── resources/           # Application properties
│   ├── pom.xml                      # Maven project file
│   └── ...
└── FinanceManager-React/        # React Frontend Application
    ├── public/
    ├── src/
    │   ├── api/                 # API client definitions
    │   ├── assets/              # Static assets (CSS, images)
    │   │   └── css/             # Component-specific stylesheets
    │   ├── components/          # React components for different views
    │   ├── context/             # React Context for authentication and user data
    │   ├── App.tsx              # Main application component
    │   ├── main.tsx             # Entry point
    │   └── ...
    ├── index.html
    ├── package.json             # Node.js dependencies and scripts
    ├── tsconfig.json            # TypeScript configuration
    └── ...
```

## Setup and Installation

Follow these steps to set up and run the Finance Manager application locally.

### Prerequisites

-   Java Development Kit (JDK) 17 or higher
-   Maven
-   Node.js (LTS version recommended)
-   npm or Yarn
-   PostgreSQL database server

### Backend Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Sishir-Stha/Finance-Manager.git
    cd Finance-Manager
    ```

2.  **Navigate to the backend directory:**
    ```bash
    cd FinanceManager-API
    ```

3.  **Configure PostgreSQL:**
    -   Create a PostgreSQL database (e.g., `financemanager_db`).
    -   Update `src/main/resources/application.properties` with your database credentials:
        ```properties
        spring.datasource.url=jdbc:postgresql://localhost:5432/financemanager_db
        spring.datasource.username=your_username
        spring.datasource.password=your_password
        spring.jpa.hibernate.ddl-auto=update
        spring.jpa.show-sql=true
        ```

4.  **Build and run the backend:**
    ```bash
    mvn clean install
    mvn spring-boot:run
    ```
    The backend API will start on `http://localhost:8080` by default.

### Frontend Setup

1.  **Navigate to the frontend directory (in a new terminal):**
    ```bash
    cd FinanceManager-React
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    # or yarn install
    ```

3.  **Start the frontend development server:**
    ```bash
    npm run dev
    # or yarn dev
    ```
    The frontend application will be accessible at `http://localhost:5173` (or another port if 5173 is in use).

## Usage

Once both the backend and frontend servers are running:
1.  Open your web browser and navigate to `http://localhost:5173`.
2.  Register a new user account or log in with existing credentials.
3.  Explore the dashboard, manage your income and expenses, set up financial plans, and view analytics.

## API Endpoints

The backend API exposes RESTful endpoints for managing users and financial data. Key endpoint categories include:

-   `/api/auth`: User registration, login, and authentication.
-   `/api/users`: User-related operations.
-   `/api/finance`: Income, expense, planning, and analytics data management.

Detailed API documentation (e.g., Swagger/OpenAPI) is not yet generated but can be inferred from the `Controller` and `DTO` classes.

## Authentication

The application uses JWT (JSON Web Tokens) for secure authentication. Upon successful login, a JWT is issued to the client, which must be included in the `Authorization` header of subsequent API requests.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

