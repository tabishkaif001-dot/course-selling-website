# Frontend Setup Instructions

This directory contains the React frontend application for the course selling website.

## Prerequisites

Before you begin, ensure you have the following installed on your local machine:

- **Node.js** (version 16.0.0 or higher)
- **npm** (version 8.0.0 or higher) or **yarn** (version 1.22.0 or higher)

## Installation

1. **Navigate to the client directory:**
   ```bash
   cd client
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or using yarn
   yarn install
   ```

## Development

### Starting the Development Server

To start the React development server:

```bash
npm start
# or using yarn
yarn start
```

The development server will start on `http://localhost:3000` by default. The page will automatically reload when you make changes to the source code.

### Building for Production

To create a production build:

```bash
npm run build
# or using yarn
yarn build
```

This creates an optimized production build in the `build` folder.

## Environment Variables

Create a `.env` file in the client directory and configure the following variables:

```env
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_PAYMENT_KEY=your_payment_gateway_key
```

## Available Scripts

- `npm start` - Runs the app in development mode
- `npm run build` - Builds the app for production
- `npm test` - Launches the test runner
- `npm run eject` - Ejects from Create React App (one-way operation)

## Project Structure

```
client/
├── public/          # Static assets
├── src/             # Source code
│   ├── components/  # Reusable components
│   ├── pages/       # Page components
│   ├── services/    # API services
│   ├── utils/       # Utility functions
│   └── App.js       # Main App component
├── package.json     # Dependencies and scripts
└── README.md        # This file
```

## Technology Stack

- **React.js** - Frontend framework
- **React Router** - Client-side routing
- **Axios** - HTTP client for API calls
- **Material-UI** or **Bootstrap** - UI component library
- **React Context** or **Redux** - State management

## API Integration

The frontend communicates with the backend API located in the `../server` directory. Ensure the backend server is running before starting the frontend development server.

## Common Issues

1. **Port already in use**: If port 3000 is busy, React will prompt to use a different port.
2. **CORS errors**: Ensure the backend API has proper CORS configuration.
3. **Environment variables**: Make sure all required environment variables are set.

## Support

For any issues or questions, please refer to the main project README or contact the development team.
