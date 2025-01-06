# Doctor Appointment System Using MERN Stack

This project is a **Doctor Appointment System** built with the **MERN** stack (MongoDB, Express.js, React.js, and Node.js). It allows patients to register, book appointments, view their profile, and manage appointments. Doctors can also view and manage appointments. This system uses **JWT** for authentication and **Role-Based Access Control** (RBAC) for patients and doctors.

## Table of Contents

1. [Features](#features)
2. [Technologies Used](#technologies-used)
3. [Project Setup](#project-setup)
   - [Frontend Setup](#frontend-setup)
   - [Backend Setup](#backend-setup)
4. [API Documentation](#api-documentation)
5. [Folder Structure](#folder-structure)
6. [Usage](#usage)
7. [Database Design](#database-design)
8. [Contributing](#contributing)
9. [License](#license)

## Features

- **User Authentication**: Secure JWT-based authentication for both patients and doctors.
- **Appointment Management**: Patients can book, view, and cancel appointments, while doctors can view and manage appointments.
- **Role-Based Access Control**: Differentiates between patient and doctor roles, providing access to role-specific pages and functionality.
- **Profile Management**: Both patients and doctors can view and edit their profiles.
- **Mobile-First Design**: The user interface is responsive and works seamlessly on all devices using **TailwindCSS**.
- **Secure Data Handling**: User data is securely handled with proper validation, encryption, and error management.
- **Appointment History**: Patients can view their past and upcoming appointments, and doctors can manage their schedules.
- **Error Handling**: Global error handling middleware implemented for both frontend and backend to handle and return consistent error messages.
  
## Technologies Used

- **Frontend**:
  - React.js
  - React Router for navigation
  - TailwindCSS for responsive UI
  - Axios for making API requests
  - JWT for authentication

- **Backend**:
  - Node.js and Express.js
  - MongoDB and Mongoose for database management
  - bcrypt.js for password hashing
  - JWT for securing APIs and authentication
  
- **Other Tools**:
  - Git and GitHub for version control
  - MongoDB Atlas for cloud-based database management
  - Heroku for backend deployment
  - Netlify for frontend deployment

## Project Setup

### Frontend Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/NileshPatil-18/Doctor-Appointment-System-Using-MERN-Stack-Technology.git
   cd Doctor-Appointment-System-Using-MERN-Stack-Technology/frontend
Install dependencies:  
npm install    

Run the React app:  
npm start  
The app will be hosted at http://localhost:3000.  

Backend Setup  
Navigate to the backend folder:  
cd Doctor-Appointment-System-Using-MERN-Stack-Technology/backend    

Install dependencies:  
npm install  

Set up environment variables: Create a .env file in the backend directory and add the following:   
MONGO_URI=<your-mongodb-uri>  
JWT_SECRET=<your-secret-key>  

Run the Node.js server:  
npm start  
The backend will be hosted at http://localhost:5000.  

MongoDB Setup   
This project uses MongoDB Atlas as the cloud database. Make sure to create a MongoDB Atlas account and replace <your-mongodb-uri> in the .env file with your connection string.  
JWT Authentication  
The backend uses JWT (JSON Web Tokens) for user authentication. After logging in, users will receive a JWT token that must be included in the Authorization header for subsequent API requests.  
API Documentation  
Authentication  
POST /api/auth/register  
Register a new user (either patient or doctor).  

Request body:
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "role": "patient"
}
  
Response:
{
  "message": "User registered successfully"
}  

POST /api/auth/login
Login and retrieve a JWT token.
Request body:
{
  "email": "john@example.com",
  "password": "password123"
}
Response:

{
  "token": "JWT_TOKEN"
}

Appointments  
POST /api/appointments/book
Book a new appointment.
Request body:
{
  "date": "2025-01-20",
  "time": "10:00",
  "doctorId": "<doctor_id>",
  "comments": "Initial consultation"
}
GET /api/appointments
Get a list of all appointments for the logged-in user (patient or doctor).
Response:
[
  {
    "appointmentId": "<appointment_id>",
    "date": "2025-01-20",
    "time": "10:00",
    "doctorId": "<doctor_id>",
    "status": "booked"
  }
]

Profile
GET /api/users/profile
Get the profile of the logged-in user.
Response:

{
  "name": "John Doe",
  "email": "john@example.com",
  "role": "patient"
}

PUT /api/users/profile
Update the profile of the logged-in user.
Request body:

{
  "name": "John Doe Updated",
  "email": "johnupdated@example.com"
}  

Folder Structure  
Here’s a quick look at the folder structure:  


Doctor-Appointment-System/  
├── backend/                # Backend folder (Node.js & Express)  
│   ├── controllers/        # API controllers  
│   ├── models/             # MongoDB models  
│   ├── routes/             # API routes  
│   ├── .env                # Environment variables  
│   └── server.js           # Backend entry point  
└── frontend/               # Frontend folder (React.js)  
    ├── public/             # Static assets  
    ├── src/                # Source code  
    │   ├── components/     # React components  
    │   ├── services/       # Axios service for API calls  
    │   └── App.js          # React app entry point  
    └── .env                # Environment variables for frontend  
Usage  
Frontend  
Visit the frontend application on Netlify (or your local setup on http://localhost:3000) to interact with the system, book appointments, and manage user profiles.  

Backend  
The backend is hosted on Heroku (or your local setup on http://localhost:5000). It provides RESTful APIs for user authentication, appointment management, and profile handling.  

Database Design    
The application uses MongoDB with the following collections:  

Users: Stores user data including name, email, password, and role.  
Appointments: Stores appointment details including patientId, doctorId, appointmentDate, and status.  
Services: Stores available services provided by doctors, such as serviceName and description.  

Contributing  
We welcome contributions to improve the project. Feel free to fork the repository, create a branch, and submit a pull request.  

Fork the repository.  
Create a new branch (git checkout -b feature-branch).  
Make your changes and commit (git commit -am 'Add new feature').  
Push to your branch (git push origin feature-branch).  
Create a Pull Request.  

License  
This project is licensed under the MIT License. See the LICENSE file for more details  
