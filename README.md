# 4-week-training-diary
# FOUR-WEEK INDUSTRIAL TRAINING DIARY

## Project: KMS-Lite – Secure Column-Level Encryption Gateway for MySQL

### 1. Introduction

During my four-week industrial training, I worked on the development of a project named **KMS-Lite (Key Management System Lite)**. The project is a proof-of-concept column-level encryption gateway designed for MySQL databases.

The main objective of this project was to understand how sensitive information can be protected at the application level using encryption, authentication, authorization and audit logging.

KMS-Lite was developed using a full-stack architecture consisting of a React 19 frontend with Vite, a FastAPI backend and a MySQL database. The backend manages authentication, employee records, encryption operations, access permissions and audit logs.

During the training, I worked on different stages of the application, beginning with project planning and database design, followed by backend development, security implementation, frontend development, API integration and documentation.

This diary presents my day-to-day learning and development activities throughout the four-week training period.

---

# WEEK 1 – PROJECT UNDERSTANDING AND INITIAL BACKEND DEVELOPMENT

**Weekly Objective:** To understand the project requirements, study its architecture, prepare the development environment, design the database and establish the initial backend structure.

## Week 1, Day 1 – Understanding the Project Requirements

### Work Completed
- I started by understanding the concept and purpose of KMS-Lite.
- Studied the importance of protecting sensitive information stored in organizational databases.
- Identified the need for column-level encryption instead of encrypting the entire database.
- Studied how an organization manages employee identities, roles and permissions.
- Identified the major modules, including authentication, employee management, encryption, audit logging and key management.

### Technical Learning
- Introduction to Key Management Systems (KMS).
- Fundamentals of database security.
- Difference between encryption at rest and application-level encryption.
- Introduction to the Principle of Least Privilege.

### Outcome / Progress
I developed a clear understanding of the problem statement and the objectives of KMS-Lite. I also identified the major modules required to develop the application.

## Week 1, Day 2 – System Architecture and Database Planning

### Work Completed
- Studied the overall architecture of KMS-Lite.
- Planned the communication between the React frontend, FastAPI backend and MySQL database.
- Identified the responsibilities of the frontend, backend and database layers.
- Planned the main database entities: users, employees, encryption_keys and audit_logs.
- Defined four application roles: admin, hr, analyst and keymanager.
- Studied the access requirements of each role.

### Technical Learning
- Three-tier application architecture.
- Relational database design.
- Entity and relationship planning.
- Role-Based Access Control (RBAC).
- Client-server communication.

### Outcome / Progress
The initial system architecture and database structure were planned. I gained an understanding of how different application modules would communicate with one another.

## Week 1, Day 3 – Development Environment Setup

### Work Completed
- Prepared the development environment for the project.
- Set up the initial FastAPI backend structure using Python.
- Prepared the React frontend environment using Vite.
- Configured the MySQL database environment.
- Reviewed the required backend and frontend dependencies.
- Organized the project directories for better code management.

### Technical Learning
- Python project environment setup.
- FastAPI framework fundamentals.
- React 19 and Vite project structure.
- MySQL installation and configuration concepts.
- Dependency management using requirements.txt and npm.

### Outcome / Progress
The initial development structure was prepared, and I understood the tools and technologies required for building the full-stack application.

## Week 1, Day 4 – MySQL Database Schema Development

### Work Completed
- Started designing the MySQL database schema.
- Created the database structure for KMS-Lite.
- Defined the users table for storing usernames, password hashes and assigned roles.
- Planned the employees table for storing employee information, including sensitive fields.
- Defined the encryption_keys table for maintaining encryption-key metadata and lifecycle status.
- Designed the audit_logs table to maintain application operation records.
- Organized the database schema in backend/schema.sql.

### Technical Learning
- MySQL database management.
- SQL table creation and data types.
- Primary keys and foreign keys.
- Database normalization concepts.
- Relational database relationships.

### Outcome / Progress
The database schema was prepared with four major tables. This established the foundation for backend data storage and management.

## Week 1, Day 5 – Initial FastAPI Backend Structure

### Work Completed
- Created the main FastAPI application structure in backend/app/main.py.
- Studied how FastAPI handles HTTP requests and responses.
- Organized the backend into separate modules for authentication, database connectivity and encryption.
- Prepared the database connection helper structure in database.py using SQLAlchemy.
- Reviewed the initial API route organization.
- Added the pinned backend dependencies in requirements.txt.

### Technical Learning
- FastAPI application structure.
- REST API fundamentals.
- HTTP methods such as GET, POST, PUT and DELETE.
- SQLAlchemy database connectivity.
- Python modules and code organization.

### Outcome / Progress
The initial backend structure was established. I gained practical knowledge of organizing a Python backend into separate modules rather than placing all functionality in one file.

### Weekly Summary – Week 1

During the first week, I focused on understanding the project requirements and preparing the development environment. I studied the architecture of KMS-Lite, planned the database entities and roles, and established the initial FastAPI, React and MySQL project structure.

By the end of the week, the project architecture, database schema and initial backend structure were prepared. This provided a foundation for implementing the security-related features in the next stage.

---

# WEEK 2 – AUTHENTICATION, ENCRYPTION AND BACKEND DEVELOPMENT

**Weekly Objective:** To implement authentication, authorization, encryption, employee management APIs and application-level audit logging.

## Week 2, Day 1 – User Authentication and Password Security

### Work Completed
- Started implementing the authentication module in backend/app/auth.py.
- Developed the authentication workflow for user registration and login.
- Implemented password hashing using bcrypt.
- Added password verification functionality for login authentication.
- Studied how passwords should be stored securely instead of saving plain-text passwords.
- Prepared the authentication endpoints in the FastAPI application.

### Technical Learning
- User authentication concepts.
- Password hashing and verification.
- bcrypt password hashing.
- Secure credential storage.
- HTTP authentication workflows.

### Outcome / Progress
The initial authentication functionality was implemented. I understood the importance of password hashing in protecting user credentials.

## Week 2, Day 2 – JWT Authentication and Role-Based Authorization

### Work Completed
- Implemented JWT bearer authentication.
- Studied how access tokens are generated and verified.
- Added authentication dependencies for protected API endpoints.
- Implemented role-checking functionality.
- Defined the four application roles: admin, hr, analyst and keymanager.
- Applied role-based restrictions to relevant backend routes.

### Technical Learning
- JSON Web Tokens (JWT).
- Bearer token authentication.
- Role-Based Access Control (RBAC).
- Authorization versus authentication.
- Protected API endpoints.

### Outcome / Progress
The backend authentication and role-based authorization structure was implemented. Different application roles could now be assigned different levels of route access.

## Week 2, Day 3 – AES-256-GCM Encryption Implementation

### Work Completed
- Started working on the encryption module in backend/app/crypto_engine.py.
- Studied symmetric encryption and authenticated encryption.
- Implemented encryption and decryption helpers using AES-256-GCM.
- Worked on the use of a master key for protecting sensitive employee information.
- Studied key wrapping and its role in encryption-key protection.
- Integrated the encryption helpers into the backend structure.

### Technical Learning
- Symmetric encryption.
- AES-256-GCM algorithm.
- Encryption and decryption processes.
- Authentication tags and data integrity.
- Master keys and key wrapping concepts.

### Outcome / Progress
The encryption helper module was developed. I gained practical knowledge of protecting sensitive application data before storing it in the database.

## Week 2, Day 4 – Employee Management APIs and Sensitive Data Protection

### Work Completed
- Developed employee creation and listing API endpoints.
- Worked on employee detail retrieval, update and delete operations.
- Integrated encryption into the employee data-handling workflow.
- Implemented encryption of sensitive fields such as SSN, salary and bank account values before database storage.
- Implemented decryption for authorized API responses.
- Used the database connection layer to interact with MySQL through SQLAlchemy.

### Technical Learning
- CRUD operations.
- FastAPI request and response handling.
- SQLAlchemy database operations.
- Application-level field encryption.
- Secure handling of sensitive employee information.

### Outcome / Progress
The main employee management APIs were implemented with encryption and decryption integrated into the data workflow. Sensitive employee values were protected before being stored in MySQL.

## Week 2, Day 5 – Audit Logging and Encryption Key Lifecycle

### Work Completed
- Implemented application-level audit logging for employee insert, select, update and delete operations.
- Developed the audit log listing endpoint.
- Started implementing encryption-key listing and generation endpoints.
- Added key status update functionality.
- Defined the key lifecycle states: pending_activation, active, suspended, retired and compromised.
- Reviewed how key-management operations should be restricted to the appropriate role.

### Technical Learning
- Application-level audit logging.
- Security monitoring and operation tracking.
- Encryption-key lifecycle management.
- Key status management.
- Security administration concepts.

### Outcome / Progress
The audit logging module and initial key-management functionality were implemented. The backend now included the main security-related modules required by the project.

### Weekly Summary – Week 2

During the second week, I concentrated on backend security and business logic. I implemented user authentication using JWT and bcrypt, introduced role-based route access and developed the AES-256-GCM encryption helpers.

I also developed the employee CRUD APIs, integrated encryption and decryption for sensitive employee fields, and implemented application-level audit logging. The encryption-key management endpoints and lifecycle status structure were also prepared.

By the end of this week, the major backend functionality of KMS-Lite had been developed.

---

# WEEK 3 – REACT FRONTEND DEVELOPMENT AND API INTEGRATION

**Weekly Objective:** To develop the user interface, implement frontend authentication and protected navigation, and connect the React application with the FastAPI backend.

## Week 3, Day 1 – React Application Structure and Login Interface

### Work Completed
- Started frontend development using React 19 and Vite.
- Reviewed the frontend source-code structure.
- Created and organized the main application routes in frontend/src/main.jsx.
- Developed the login page for user authentication.
- Prepared the frontend API communication structure.
- Studied how React components are used to build reusable interfaces.

### Technical Learning
- React 19 fundamentals.
- Vite development environment.
- JSX and functional components.
- React application routing.
- Component-based frontend development.

### Outcome / Progress
The initial frontend application structure and login interface were prepared. I gained practical experience organizing a React application into separate components and pages.

## Week 3, Day 2 – Authentication Context and Protected Routes

### Work Completed
- Developed the shared authentication context in AuthContext.jsx.
- Implemented frontend handling of the authentication token and user information.
- Used localStorage to maintain the token and user state.
- Configured the Axios API client in frontend/src/api/axios.js.
- Added JWT bearer token attachment to API requests.
- Implemented the ProtectedRoute component to restrict access to unauthenticated users and unauthorized roles.
- Added handling for HTTP 401 responses to redirect users to the login page.

### Technical Learning
- React Context API.
- Shared application state.
- localStorage.
- Axios interceptors.
- Protected routing.
- JWT integration between frontend and backend.

### Outcome / Progress
The frontend authentication structure was implemented. The application could maintain shared authentication state and enforce login and role requirements through protected routes.

## Week 3, Day 3 – Role-Aware Navigation and Dashboard Development

### Work Completed
- Developed the shared navigation layout in Navbar.jsx.
- Implemented role-aware sidebar navigation.
- Organized navigation options according to the logged-in user's role.
- Developed the Dashboard page.
- Prepared role-specific dashboard views.
- Worked on displaying relevant application information in an organized interface.
- Applied styling through frontend/src/index.css.

### Technical Learning
- Conditional rendering in React.
- Role-based UI components.
- Reusable navigation components.
- Dashboard layout design.
- CSS styling and frontend organization.

### Outcome / Progress
The main dashboard and role-aware navigation interface were developed. The frontend structure became more organized and easier to navigate.

## Week 3, Day 4 – Employee Management Interface

### Work Completed
- Developed the Employees page to display employee records.
- Created the Add Employee page with a form for entering employee information.
- Connected the employee pages to the backend API through Axios.
- Implemented the frontend functionality for employee record operations.
- Worked on displaying employee information in tables.
- Added loading and error states to improve the user experience.
- Connected the frontend forms with the corresponding backend endpoints.

### Technical Learning
- React forms and controlled inputs.
- Axios GET and POST requests.
- API request and response handling.
- Dynamic data rendering.
- Frontend and backend integration.

### Outcome / Progress
The employee management interface was developed and connected to the backend APIs. Users could interact with employee records through the React interface.

## Week 3, Day 5 – Audit Logs and Key Management Interface

### Work Completed
- Developed the Audit Logs page to display application-level operation records.
- Connected the page to the backend audit log listing endpoint.
- Developed the Key Management page.
- Integrated the encryption-key listing, generation and status update endpoints.
- Added interface elements for displaying key lifecycle statuses.
- Organized page actions and information according to user permissions.
- Reviewed the frontend navigation and page structure.

### Technical Learning
- Displaying audit records in React.
- API integration for administrative modules.
- Dynamic status display.
- Role-aware application interfaces.
- Managing asynchronous API responses.

### Outcome / Progress
The audit logging and key-management pages were developed and connected to their respective backend endpoints. The main frontend modules of KMS-Lite were now in place.

### Weekly Summary – Week 3

During the third week, I focused on developing the React frontend and integrating it with the FastAPI backend. I implemented the login interface, shared authentication context, protected routes and role-aware navigation.

I also developed the dashboard, employee management pages, audit logs and key management interface. Axios was used for communication between the frontend and backend, while loading and error states were incorporated into the pages.

By the end of the week, the major frontend modules had been developed and connected to the backend APIs.

---

# WEEK 4 – INTEGRATION, VALIDATION, DEPLOYMENT CONFIGURATION AND DOCUMENTATION

**Weekly Objective:** To refine the application, review security and integration behavior, prepare containerization configurations, improve documentation and identify future enhancements.

## Week 4, Day 1 – Input Validation and Error Handling

### Work Completed
- Reviewed the request validation structure in the FastAPI backend.
- Worked with Pydantic models for validating incoming API data.
- Reviewed email validation for user and employee-related inputs.
- Implemented positive salary validation.
- Reviewed the handling of invalid requests and API errors.
- Improved the frontend loading and error-state handling.
- Reviewed the Axios response interceptor for unauthorized requests.

### Technical Learning
- Pydantic validation.
- Data validation in FastAPI.
- HTTP status codes.
- API error handling.
- Frontend error-state management.

### Outcome / Progress
The request validation and error-handling structure was refined. I understood how proper input validation helps maintain data consistency and improve application reliability.

## Week 4, Day 2 – Security Review and Key Lifecycle Management

### Work Completed
- Reviewed the JWT authentication and role-checking implementation.
- Examined access restrictions for the admin, hr, analyst and keymanager roles.
- Reviewed the encryption and decryption workflow for sensitive employee fields.
- Studied the five encryption-key lifecycle states.
- Reviewed the key listing, generation and status update functionality.
- Examined the handling of environment variables and sensitive configuration values.
- Reviewed the use of .gitignore to exclude environment-specific credentials.

### Technical Learning
- Application security review.
- Secure configuration management.
- Principle of Least Privilege.
- Encryption-key lifecycle concepts.
- Role-based access restrictions.

### Outcome / Progress
The security structure of the application was reviewed. I also identified the difference between managing key metadata and implementing complete cryptographic key rotation.

## Week 4, Day 3 – Frontend and Backend Integration Review

### Work Completed
- Reviewed communication between the React frontend and FastAPI backend.
- Examined the Axios configuration for attaching JWT bearer tokens.
- Reviewed authentication state handling and protected page access.
- Checked the data flow for employee creation, retrieval, updating and deletion.
- Reviewed the connection between employee operations and audit logging.
- Examined the integration of the audit log and key-management interfaces with backend endpoints.
- Reviewed API response handling and page status displays.

### Technical Learning
- Full-stack application architecture.
- Frontend and backend integration.
- REST API communication.
- Authentication token handling.
- Application-level security monitoring.

### Outcome / Progress
The major frontend and backend integration points were reviewed. I developed a better understanding of how authentication, database operations, encryption and user-interface components work together.

## Week 4, Day 4 – Docker Configuration and Technical Documentation

### Work Completed
- Prepared and reviewed the backend Dockerfile for packaging the FastAPI application.
- Reviewed the frontend Dockerfile for building the Vite application and serving it through Nginx.
- Worked with the frontend Nginx configuration for frontend and API routing.
- Reviewed the Vite configuration.
- Prepared and reviewed the Docker Compose configuration for MySQL, backend and frontend services.
- Reviewed the persistent MySQL volume and database health-check configuration.
- Updated the project documentation with architecture, setup instructions, roles and environment variables.

### Technical Learning
- Docker fundamentals.
- Dockerfiles and container configuration.
- Docker Compose.
- Nginx web server configuration.
- Environment variables and application configuration.
- Technical documentation.

### Outcome / Progress
The containerization and deployment configuration files were prepared and reviewed. The setup and architecture documentation was also improved. The configuration files were not treated as proof of a successful container deployment.

## Week 4, Day 5 – Final Project Review and Learning Summary

### Work Completed
- Reviewed the overall KMS-Lite project architecture.
- Organized the final project modules and documentation.
- Reviewed the implemented authentication, encryption, employee management and audit logging features.
- Identified incomplete areas in key rotation and cryptographic key management.
- Reviewed the limitations of application-level audit logging.
- Identified field-level access control as a future enhancement.
- Prepared a summary of the technical concepts and development experience gained during the training.

### Technical Learning
- Software development lifecycle.
- Security-focused application development.
- Full-stack project organization.
- Technical documentation.
- Identifying limitations and planning future improvements.

### Outcome / Progress
The four-week development diary was completed. I gained practical knowledge of building a full-stack security-focused application using React, FastAPI and MySQL. I also developed a better understanding of application-level encryption, authentication, authorization and audit logging.

### Weekly Summary – Week 4

During the final week, I concentrated on refining the application, reviewing its security structure and preparing the deployment configuration and documentation.

I worked on Pydantic validation, API error handling, authentication review, key lifecycle behavior and frontend-backend integration. I also reviewed the Dockerfiles, Nginx configuration and Docker Compose setup.

Finally, I examined the known limitations and identified areas for future development, including key rotation, field-level access control and database-level audit monitoring.

---

# 2. Skills and Technologies Learned

Throughout the four-week training period, I gained practical knowledge of several technologies and development concepts.

## Frontend Development
- React 19
- JavaScript and JSX
- Vite
- React Context API
- React Router / protected routing
- Axios
- HTML and CSS
- localStorage
- Component-based UI development

## Backend Development
- Python
- FastAPI
- REST API development
- Pydantic
- SQLAlchemy
- JWT authentication
- bcrypt password hashing
- Role-Based Access Control

## Database Management
- MySQL
- SQL queries
- Relational database design
- Database schema development
- CRUD operations
- Database connectivity

## Security and Encryption
- AES-256-GCM encryption
- Encryption and decryption
- Key wrapping concepts
- Master key management
- Authentication and authorization
- Application-level audit logging
- Encryption-key lifecycle management
- Principle of Least Privilege

## Deployment and Development Tools
- Docker
- Docker Compose
- Nginx
- Git and GitHub
- Visual Studio Code
- Environment variable configuration
- Technical documentation

---

# 3. Challenges and Limitations

During the development of KMS-Lite, I studied several security and implementation challenges. Some of these areas were addressed through the implemented application functionality, while others remain part of the project's future scope.

### 1. Secure Storage of Sensitive Information

One of the major challenges was protecting sensitive employee information in the MySQL database. I addressed this through application-level AES-256-GCM encryption before storing sensitive fields.

### 2. Authentication and Authorization

Another challenge was ensuring that different users could access only the routes permitted for their assigned roles. JWT authentication and role-based route checks were implemented to manage this requirement.

### 3. Audit Logging Limitations

The current audit logging implementation records operations performed through the FastAPI application. It does not capture direct database access that bypasses the application. Database-level monitoring requires additional mechanisms such as MySQL Enterprise Audit or equivalent solutions.

### 4. Field-Level Access Control

The current RBAC implementation primarily controls access at the route level. More detailed field-level restrictions, such as allowing an analyst to view employee information without revealing an SSN, remain future scope.

### 5. Encryption-Key Rotation

Complete key rotation and re-encryption of existing employee records using a new key have not yet been implemented. The current system manages key metadata and lifecycle statuses, while per-entry cryptographic key material generation is still in progress.

### 6. Session Management

The current login mechanism uses JWT-based sessions without refresh tokens. Sessions expire after eight hours, and refresh-token functionality is a possible future enhancement.

### 7. Deployment and Containerization

Dockerfiles, Nginx configuration and Docker Compose configuration were prepared as part of the project structure. However, the existence of these files does not establish that a complete containerized deployment was successfully executed.

---

# 4. Future Scope

The following improvements can make KMS-Lite more suitable for a production-oriented environment:

- Implement complete encryption-key rotation and automatic re-encryption of existing records.
- Complete per-entry cryptographic key material management.
- Introduce field-level access control for sensitive employee information.
- Integrate database-level auditing to monitor direct MySQL access.
- Implement refresh tokens and improved session management.
- Introduce stronger security monitoring and alerting.
- Add automated backend and frontend testing.
- Perform a complete containerized deployment and security assessment.
- Improve key recovery and secure backup procedures.

---

# 5. Final Project Summary

During my four-week industrial training, I worked on the development of **KMS-Lite – Secure Column-Level Encryption Gateway for MySQL**.

The project helped me understand how a security-focused full-stack application can be developed using modern web technologies.

I worked with React 19 and Vite to develop the frontend, FastAPI to implement the backend APIs, and MySQL to store application data. I also gained practical knowledge of JWT authentication, bcrypt password hashing, Role-Based Access Control and AES-256-GCM encryption.

One of the most important aspects of this project was understanding how sensitive employee information can be encrypted before it is stored in a database and decrypted for authorized API responses.

I also learned how application-level audit logging can help maintain a record of employee data operations and how encryption-key lifecycle management can be incorporated into a security-focused application.

Apart from development, I gained knowledge of Docker configuration, Nginx, environment variables, project documentation and full-stack application architecture.

The project is a proof of concept and still has several areas for improvement, particularly complete key rotation, field-level access control and database-level auditing.

Overall, this training experience improved my programming skills, problem-solving abilities and understanding of secure software development. It also gave me practical exposure to developing a complete application by combining frontend development, backend programming, database management and security concepts.

---

# 6. Conclusion

The four-week training period was a valuable learning experience for me. It provided an opportunity to apply theoretical concepts to a practical software development project.

By developing KMS-Lite, I improved my understanding of full-stack development and learned the importance of security in modern applications. I also understood that building a professional software product requires proper planning, organized coding, validation, documentation and continuous improvement.

This project has strengthened my technical foundation and motivated me to continue learning advanced concepts in software engineering, database security and application development.
