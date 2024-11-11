### **POE Goals for APDS**
Team members:
Azania Ncube- ST10036066(PM)
Adrian Silver -ST10082035
Mushfeeq Hartnick - ST10082857
Cameron Colley - ST10037966

All team members are from Group two. 

Within this folder there is
	###This readme file
	1. A folder showing the CircleCi config.yml tests screenshots
	2. The folder taht will be used to open VS Code(Secure  Banking Solution and Co-APDS)
	3. A word document describing the ethical use of AI throughout this assignment. The document explain how AI has 	been helpful with handling new experienced issues. 
	4. folders labeled 'Project using circleci', is the project that uses circleci however the was a duplicate within the read only files therefore the backup has been included in the folder labeled 'Project after changes made' which is another folder without the duplicate keys.
 5. Meet the team-Secure Banking Solutions and Co folder that has a txt file with the student group members
	6. Video by the team members that has a txt file that has the Youtube link of the video. 
Important links:
	Please copy this GitHub link if you need to check out the GitHub organization and repo used for this POE.
		Repo with circleci: https://github.com/ST10036066/secure-banking-solutions-and-Co-APDS
		Org repo used for sharing files: https://github.com/Secure-Banking-Solution-and-Co
  	The Youtube video link. Unfortunately, the video was too large to paste within the submission folder however the video is still available to watch on Youtube using the link: https://youtu.be/f49spL-hCbk?si=bavwnebkAWXlhLEk

----------------------------------------------------------------------------------------------------------------------
The primary objectives are:
- Create a **secure customer portal** for managing transactions.
- Implement **strict security protocols** throughout.
- Enable **bank employees** to manage and verify transactions before submission to SWIFT.

### **Tasks and Assignments**

#### **1. User Management Setup**

- **Assigned to Adrian**
  
  **Steps:**
  - **Step 1**: Implement a pre-configured list of users since no registration process is needed. These should be "hardcoded" or pulled from an initial data source in the system.
  - **Step 2**: Set up the login functionality to authenticate users based on this predefined list. Ensure that employees log in using credentials stored securely (e.g., in the database).
  - **Step 3**: Ensure that users have specific roles or permissions, if necessary, to restrict access to certain features (like viewing and verifying transactions).

#### **2. Password Security (Hashing and Salting)**

- **Assigned to Mushfeeq**
  Feedback: Mushfeeq is a team player who constantly kept updating the whole group. 
  **Steps:**
  - **Step 1**: Integrate a password hashing library like `bcryptjs` (for Node.js) to hash and salt passwords.
  - **Step 2**: Apply hashing and salting to all user passwords before storing them in the database.
  - **Step 3**: Test the login function to verify that passwords are securely hashed and cannot be accessed in plain text.

#### **3. Input Whitelisting with Regex Patterns**

- **Assigned to Cameron**
  There is room for improvement in terms of communication
  **Steps:**
  - **Step 1**: Identify all input fields that need validation, including login fields and transaction details.
  - **Step 2**: Develop basic regular expressions (RegEx) to restrict unwanted characters (like SQL injection markers, `<script>` tags, etc.).
  - **Step 3**: Apply these RegEx patterns to sanitize and validate user inputs on the client and server side.
  - **Step 4**: Test inputs with various patterns to ensure the application rejects any potentially harmful input.

#### **4. Secure Traffic with SSL and Security Libraries and MongoDB**

- **Assigned to Azania (PM)**
  
  **Steps:**
  - **Step 1**: Obtain or generate a valid SSL certificate and private key (consult with the IT/security team if necessary).
  - **Step 2**: Configure the server to enforce SSL. Make sure all HTTP traffic is redirected to HTTPS.
  - **Step 3**: Install and configure `Express Brute` to protect against brute force attacks and `Helmet` for setting secure HTTP headers.
  - **Step 4**: Perform a security audit to verify that SSL is properly enforced across the portal.
	-**Step 5**: Using the module lab guide ensure the connection string, MongoDB cluster and collection of hard coded employees is added

#### **5. Transaction Processing 

- **Assigned to Adrian and Cameron**
  Feedback: Both team members need to improve in communication as discussed in the group. Updates were difficult to get from them but as a team we tried working with what they had at the last moment they could deliver

  **Steps:**
  - **Step 1 (Adrian)**: Design and set up a secure database schema to store transaction details, ensuring encryption for sensitive data fields.
  - **Step 2 (Cameron)**: Build the interface for employees to view and verify transactions, displaying key information like payee account details and SWIFT codes.
  - **Step 3 (Adrian and Cameron)**: Implement a "verified" button for each transaction entry and a "Submit to SWIFT" button to complete the transaction process.
  - **Step 4 (Adrian)**: After submission, ensure the transaction status is updated and flagged for SWIFT transfer.

#### **6. Final Review and Testing**

- **All Team Members**

  **Steps:**
  - **Step 1**: Complete unit testing for each feature and conduct a brief code review session.
  - **Step 2**: Coordinate with Azania to ensure everything meets security and functionality requirements.
  - **Step 3**: Document your code changes and update the README to reflect any setup or operational instructions.
  - **Step 4**: Prepare for a quick demo on Monday, showcasing the portal's core functionality and security features.

Feedback of the entire group:
There is room for improvement for communication and staying up to datw with what the project manager sends via the group. On the good side, group work challenged the project manager to push the team members as best as the project manager could do. 
----------------------------------------------------------------------------------------
The hardcoded employee details. Order starts from username followed by the password:
PeterHlope, Banking@12Aw3z0m3
AmahleVilakazi,Tr0stM3!
ZuriKamau, S2v1ings*
AlexMerwer, c0nn3ct#M0n3y
---------------------------------------------------------------------------------------
Thank you for reaching this far
---------------------------------------------------------------------------------------
###Additional information that has been useful and used :
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

-----------------------------------------------------------------------------------------------------------------------------
