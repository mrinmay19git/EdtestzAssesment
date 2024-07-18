# Edtestz Assessment Appointment Application

## Overview

This application allows users to register, sign in, book appointments, and view appointment history. The project is divided into backend and frontend sections. The backend is built with Node.js, Express, and Sequelize, while the frontend is built with React.js.

## Prerequisites

- Node.js
- npm

## Backend Setup

1. **Initialize Project**:
    ```bash
    mkdir appointment-app
    cd appointment-app
    mkdir backend
    cd backend
    npm init -y
    ```

2. **Install Dependencies**:
    ```bash
    npm install express sequelize sqlite3 bcryptjs jsonwebtoken dotenv cors
    ```

3. **Setup Project Structure**:
    ```bash
    mkdir config controllers middleware models routes
    touch server.js .env
    ```

4. **Configure Environment Variables**:
    Create a `.env` file at the root of your backend directory and add:
    ```plaintext
    PORT=5000
    JWT_SECRET=your_jwt_secret
    ```

5. **Database Connection**:
    Create `config/db.js` and set up Sequelize to connect to SQLite or write your own queries.

6. **Define Models**:
    Create `models/User.js` and `models/Appointment.js` with Sequelize to define your database schema.

7. **Middleware for Authentication**:
    Create `middleware/auth.js` to handle JWT authentication.

8. **User Controller**:
    Implement signup and signin functionality in `controllers/userController.js`.

9. **Appointment Controller**:
    Implement appointment creation and fetching functionality in `controllers/appointmentController.js`.

10. **Define Routes**:
    Create routes in `routes/user.js` and `routes/appointment.js` to handle user and appointment-related API requests.

11. **Setup Server**:
    In `server.js`, set up the Express server, connect to the database, and define your routes.

12. **Run Backend Server**:
    Start your backend server:
    ```bash
    node server.js
    ```

## Frontend Setup

1. **Initialize Project**:
    ```bash
    cd ..
    npx create-react-app client
    cd client
    ```

2. **Install Dependencies**:
    ```bash
    npm install axios react-router-dom
    ```

3. **Setup Project Structure**:
    ```bash
    mkdir src/components src/pages src/context src/utils
    touch src/context/AuthContext.js src/utils/PrivateRoute.js
    ```

4. **Authentication Context**:
    Set up context to manage authentication state in `src/context/AuthContext.js`.

5. **Private Route Component**:
    Create a utility component to protect routes in `src/utils/PrivateRoute.js`.

6. **SignUp and SignIn Components**:
    Implement SignUp and SignIn forms in `src/pages/SignUp.js` and `src/pages/SignIn.js`.

7. **Booking and Appointment History Components**:
    Implement Booking and Appointment History components in `src/pages/Booking.js` and `src/pages/AppointmentHistory.js`.

8. **Routing Setup**:
    Configure routes in `src/App.js` using React Router.

9. **Styling**:
    Apply CSS to ensure the application is responsive and visually appealing.

## Integrating Frontend with Backend

1. **Proxy Setup**:
    In `client/package.json`, add a proxy to your backend server:
    ```json
    "proxy": "http://localhost:5000"
    ```

2. **API Requests**:
    Use Axios to make HTTP requests from your React components to the backend API endpoints.

3. **Authentication Flow**:
    Store the JWT token in local storage or cookies and include it in the Authorization header of protected API requests.

## Final Steps

1. **Run Frontend**:
    Start your React development server:
    ```bash
    npm start
    ```

2. **Test the Application**:
    Ensure the frontend communicates properly with the backend, user authentication works, appointments can be booked, and appointment history is displayed.

3. **Documentation**:
    Create a README file with setup instructions, describing how to run the application locally, including any necessary environment variables and commands.
