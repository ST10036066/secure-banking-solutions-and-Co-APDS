# Project Structure
The project includes:
- A folder labeled **APDS** containing the complete source code.
- The **GitHub repository** link for the project.
- A **README** file outlining the steps for setup and usage.

## Team Members
This project was developed by the following team members:
- Azania Aria - ST10036066
- Mushfeeq Hartnick - ST10082857
- Adrian Silver - ST10082035
- Cameron Colley - ST10037966

## Repository Link
(https://github.com/ST10036066/secure-banking-solutions-and-Co-APDS)
# Secure Banking Solutions and Co  
A secure banking web application developed for the APDS team project, part 2.

## Project Overview
This project is a secure banking solution designed to ensure the safety and security of users' financial data. The application is built using Angular for the frontend and MongoDB for data storage.

## Frontend
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 18.2.7.

### Development Server
Run `ng serve` for a development server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

### Code Scaffolding
Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

### Build
Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

### Running Unit Tests
Run `ng test` to execute unit tests via [Karma](https://karma-runner.github.io).

### Running End-to-End Tests
Run `ng e2e` to execute end-to-end tests via a platform of your choice. You will need to add a package that implements end-to-end testing capabilities.

## Backend Security Features

### User Input Validation
Utilizes Joi to validate user input before processing.  
**Installation**: `npm install joi`

### Password Hashing and Salting
All passwords are securely hashed and salted using bcryptjs before being stored in the database. This ensures that passwords are not stored in plain text, protecting against data breaches.
- **Hashing Library**: bcryptjs
- **Installation**: `npm install bcryptjs`
- **Implementation**: Passwords are hashed during the registration process, and the hashed passwords are verified during login.

### User Authentication
JSON Web Tokens (JWT) are used for authentication.  
**Installation**: `npm install jsonwebtoken`

### Middleware for Authentication
Protects sensitive routes by verifying the JWT to ensure only authenticated users can access certain endpoints.

### Error Handling
Error handling has been implemented to catch and respond to errors gracefully, ensuring a better user experience and traceability of issues.

## Environment Variables
Sensitive information, such as database connection strings and API keys, are stored in environment variables to enhance security.

## Additional Backend Instructions

### Running the Backend Server
1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Start the Server**:
   ```bash
   node app.js
   ```
   The backend server will run on `http://localhost:3000`.

### API Endpoints

#### Register User
- **URL**: `/register`
- **Method**: `POST`
- **Description**: Registers a new user by hashing and salting the password before storing it.
- **Request Body**:
  ```json
  {
      "username": "testUser",
      "password": "mySecurePassword"
  }
  ```
- **Response**:
  - `201 Created`: `User registered successfully`
  - `400 Bad Request`: `Username and password are required`
  - `500 Internal Server Error`: If there was a problem with the hashing process.

#### User Login
- **URL**: `/login`
- **Method**: `POST`
- **Description**: Authenticates a user by comparing the entered password with the stored hashed password.
- **Request Body**:
  ```json
  {
      "username": "testUser",
      "password": "mySecurePassword"
  }
  ```
- **Response**:
  - `200 OK`: `Login successful`
  - `400 Bad Request`: `User not found` or `Incorrect password`
  - `500 Internal Server Error`: If there was a problem during verification.
