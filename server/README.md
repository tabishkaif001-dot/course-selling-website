# Backend Setup Instructions

This directory contains the Node.js backend API for the course selling website.

## Prerequisites

Before you begin, ensure you have the following installed on your local machine:

- Node.js (version 16.0.0 or higher)
- npm (version 8.0.0 or higher) or yarn (version 1.22.0 or higher)
- MongoDB (version 4.4 or higher) or MongoDB Atlas account

## Installation

1. Navigate to the server directory:
```bash
cd server
```

2. Install dependencies:
```bash
npm install
# or using yarn
yarn install
```

## Environment Configuration

Create a `.env` file in the server directory and configure the following variables:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/course-selling-db
# For MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/course-selling-db

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key
JWT_EXPIRE=30d

# Email Configuration (for notifications)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_EMAIL=your-email@gmail.com
SMTP_PASSWORD=your-email-password

# Payment Gateway (Stripe/Razorpay)
STRIPE_SECRET_KEY=sk_test_your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=pk_test_your_stripe_publishable_key

# File Upload Configuration
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

## Development

### Starting the Development Server

To start the Node.js development server:

```bash
npm run dev
# or using yarn
yarn dev
```

The development server will start on `http://localhost:5000` by default. The server will automatically restart when you make changes to the source code (using nodemon).

### Starting in Production Mode

To start the server in production mode:

```bash
npm start
# or using yarn
yarn start
```

## Available Scripts

- `npm start` - Runs the server in production mode
- `npm run dev` - Runs the server in development mode with auto-restart
- `npm test` - Runs the test suite
- `npm run lint` - Lints the code using ESLint
- `npm run format` - Formats the code using Prettier

## Project Structure

```
server/
├── config/          # Configuration files
├── controllers/     # Route controllers
├── middleware/      # Custom middleware functions
├── models/          # Database models
├── routes/          # API routes
├── utils/           # Utility functions
├── uploads/         # File upload directory
├── .env            # Environment variables
├── server.js       # Main server file
└── package.json    # Dependencies and scripts
```

## Technology Stack

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Multer** - File upload handling
- **Cloudinary** - Image hosting service
- **Stripe/Razorpay** - Payment processing
- **Nodemailer** - Email sending
- **Cors** - Cross-origin resource sharing
- **Helmet** - Security headers
- **Express Rate Limit** - Rate limiting

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/forgot-password` - Forgot password
- `PUT /api/auth/reset-password/:token` - Reset password

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `GET /api/users/courses` - Get enrolled courses

### Courses
- `GET /api/courses` - Get all courses
- `GET /api/courses/:id` - Get course by ID
- `POST /api/courses` - Create new course (admin only)
- `PUT /api/courses/:id` - Update course (admin only)
- `DELETE /api/courses/:id` - Delete course (admin only)

### Orders
- `POST /api/orders` - Create new order
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get order by ID
- `PUT /api/orders/:id/payment` - Update payment status

## Database Setup

### Local MongoDB

1. Install MongoDB Community Edition
2. Start MongoDB service:
   ```bash
   mongod
   ```
3. The application will connect to `mongodb://localhost:27017/course-selling-db`

### MongoDB Atlas (Cloud)

1. Create account at [MongoDB Atlas](https://www.mongodb.com/atlas)
2. Create a new cluster
3. Get connection string and update `MONGODB_URI` in `.env`
4. Whitelist your IP address

## Security Features

- JWT-based authentication
- Password hashing with bcrypt
- Rate limiting to prevent abuse
- CORS configuration
- Security headers with Helmet
- Input validation and sanitization
- Environment variable protection

## Testing

Run the test suite:

```bash
npm test
# or using yarn
yarn test
```

For test coverage:

```bash
npm run test:coverage
# or using yarn
yarn test:coverage
```

## Deployment

### Environment Variables for Production

Ensure all environment variables are properly set in your production environment:

- Set `NODE_ENV=production`
- Use secure JWT secrets
- Configure production database URI
- Set up proper CORS origins
- Configure email service credentials
- Set up payment gateway keys

### Common Deployment Platforms

- **Heroku**: Use Heroku Config Vars for environment variables
- **Vercel**: Configure environment variables in project settings
- **DigitalOcean**: Use App Platform or Droplets
- **AWS**: Use Elastic Beanstalk or EC2 instances

## Common Issues

1. **Database Connection Errors**: Ensure MongoDB is running and connection string is correct
2. **Port Already in Use**: Change PORT in `.env` file or kill the process using the port
3. **JWT Errors**: Verify JWT_SECRET is set and consistent
4. **File Upload Issues**: Check Cloudinary credentials and file size limits
5. **Payment Errors**: Verify payment gateway API keys and webhook endpoints

## API Documentation

For detailed API documentation, start the server and visit:
- Development: `http://localhost:5000/api-docs`
- Or refer to the Postman collection in the `/docs` folder

## Support

For any issues or questions, please refer to the main project README or contact the development team.

## Contributing

When making changes to the backend:

1. Follow the existing code structure
2. Add proper error handling
3. Include appropriate tests
4. Update API documentation
5. Ensure environment variables are documented
