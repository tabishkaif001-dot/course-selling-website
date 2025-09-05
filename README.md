# course-selling-website

A fully functional course selling website built with modern web technologies. Features user authentication, course management, payment integration, and responsive design for optimal learning experience.

## Project Structure & Technology Stack

This application follows a modern full-stack architecture with clear separation of concerns:

### Frontend (Client)
- **Technology**: React.js
- **Location**: `/client` directory
- **Purpose**: User interface and client-side logic for the course selling platform

### Backend (Server)
- **Technology**: Node.js with Express.js framework
- **Location**: `/server` directory
- **Purpose**: REST API, authentication, business logic, and server-side operations

### Database
- **Technology**: MongoDB
- **Purpose**: Data persistence for users, courses, orders, and application state

### Architecture Overview
```
course-selling-website/
├── client/          # React frontend application
├── server/          # Node.js/Express backend API
└── README.md        # Project documentation
```

The frontend communicates with the backend through RESTful APIs, while the backend handles all database operations and business logic using MongoDB as the primary data store.
