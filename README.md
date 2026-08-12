# Food Recipe Auth App

A complete authentication-based web application built with Node.js, Express.js, MongoDB, and vanilla JavaScript. Features user registration, login, profile management, and protected routes with JWT authentication.

## 🚀 Features

- **Complete Authentication System**
  - User registration with validation
  - Login/logout functionality
  - JWT token-based authentication
  - Password hashing with bcrypt
  - Protected routes and middleware

- **Frontend Pages**
  - Login page with form validation
  - Registration page with password confirmation
  - Home dashboard with food recipe features
  - User profile management
  - Settings page with account information

- **Backend API**
  - RESTful API endpoints
  - Input validation with express-validator
  - Error handling and proper HTTP status codes
  - MongoDB integration with Mongoose
  - Secure password storage

## 🛠️ Tech Stack

### Frontend
- HTML5
- CSS3 with modern styling and animations
- Vanilla JavaScript (ES6+)
- Responsive design

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose ODM
- JWT for authentication
- bcrypt for password hashing
- express-validator for input validation

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or later)
- [MongoDB](https://www.mongodb.com/) (v4.4 or later)
- [npm](https://www.npmjs.com/) (comes with Node.js)

## ⚡ Quick Start

### 1. Clone or Download the Project

```bash
# If cloning from a repository
git clone <repository-url>
cd food-recipe-auth-app

# Or if you received the project files, navigate to the project directory
cd my-project
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Edit the .env file with your settings (optional - defaults work for local development)
```

### 3. Database Setup

Make sure MongoDB is running on your system:

```bash
# Start MongoDB (varies by installation method)
# For Windows with MongoDB as a service:
net start MongoDB

# For macOS with Homebrew:
brew services start mongodb-community

# For Linux:
sudo systemctl start mongod
```

### 4. Start the Application

```bash
# From the backend directory, start the server
npm start

# For development with auto-reload:
npm run dev
```

The application will be available at: **http://localhost:5000**

## 📁 Project Structure

```
my-project/
├── frontend/
│   ├── css/
│   │   └── style.css          # Main stylesheet
│   ├── js/
│   │   └── auth.js            # Authentication JavaScript
│   ├── login.html             # Login page
│   ├── register.html          # Registration page
│   ├── home.html              # Main dashboard
│   ├── profile.html           # User profile page
│   └── settings.html          # Settings page
├── backend/
│   ├── config/
│   │   └── db.js              # Database configuration
│   ├── controllers/
│   │   ├── authController.js  # Authentication logic
│   │   └── userController.js  # User management logic
│   ├── middleware/
│   │   └── auth.js            # JWT authentication middleware
│   ├── models/
│   │   └── User.js            # User database model
│   ├── routes/
│   │   ├── auth.js            # Authentication routes
│   │   └── user.js            # User routes
│   ├── .env.example           # Environment variables template
│   ├── package.json           # Dependencies and scripts
│   └── server.js              # Main server file
└── README.md                  # Project documentation
```

## 🔧 API Endpoints

### Authentication Routes

| Method | Endpoint | Description | Protected |
|--------|----------|-------------|-----------|
| POST | `/api/auth/register` | Register new user | ❌ |
| POST | `/api/auth/login` | Login user | ❌ |
| GET | `/api/auth/me` | Get current user | ✅ |

### User Routes

| Method | Endpoint | Description | Protected |
|--------|----------|-------------|-----------|
| GET | `/api/user/profile` | Get user profile | ✅ |
| PUT | `/api/user/profile` | Update user profile | ✅ |

## 🔐 Authentication Flow

1. **Registration**: User creates account with name, email, and password
2. **Login**: User logs in with email and password
3. **Token Storage**: JWT token is stored in localStorage
4. **Route Protection**: Protected pages check for valid token
5. **Auto-Redirect**: Invalid/expired tokens redirect to login
6. **Logout**: Clears token and redirects to login

## 🎨 Frontend Features

- **Responsive Design**: Works on desktop and mobile devices
- **Modern UI**: Clean, modern interface with gradients and animations
- **Form Validation**: Client-side and server-side validation
- **Loading States**: Visual feedback during API calls
- **Error Handling**: User-friendly error messages
- **Auto-Redirect**: Smart routing based on authentication state

## 🔒 Security Features

- **Password Hashing**: Passwords are hashed with bcrypt
- **JWT Authentication**: Secure token-based authentication
- **Input Validation**: Server-side validation for all inputs
- **Protected Routes**: Middleware protection for sensitive endpoints
- **CORS Enabled**: Cross-origin resource sharing configured
- **No Password Exposure**: Passwords never returned in API responses

## 🚀 Deployment

### Environment Variables for Production

Create a `.env` file in the backend directory:

```env
MONGODB_URI=mongodb://localhost:27017/auth_app
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
PORT=5000
NODE_ENV=production
```

### Production Deployment Steps

1. **Update Environment Variables**: Set production values in `.env`
2. **Database**: Ensure MongoDB is accessible from your production server
3. **Build**: No build step needed for this vanilla JS frontend
4. **Start**: Use `npm start` to run the production server
5. **Process Manager**: Consider using PM2 for process management

### Using PM2 (Recommended)

```bash
# Install PM2 globally
npm install -g pm2

# Start the application
pm2 start backend/server.js --name "food-recipe-app"

# Save PM2 configuration
pm2 save

# Setup PM2 to start on boot
pm2 startup
```

## 🔍 Troubleshooting

### Common Issues

1. **MongoDB Connection Error**
   - Ensure MongoDB is running
   - Check the MONGODB_URI in your .env file
   - Verify MongoDB is accepting connections

2. **Port Already in Use**
   - Change the PORT in .env file
   - Kill the process using the port: `npx kill-port 5000`

3. **JWT Token Issues**
   - Clear localStorage in browser developer tools
   - Ensure JWT_SECRET is set in .env

4. **CORS Errors**
   - Check if the frontend is being served from the same origin
   - Verify CORS configuration in server.js

### Debug Mode

To run in debug mode:

```bash
# Enable debug logging
DEBUG=* npm run dev
```

## 📱 Usage

1. **Visit**: http://localhost:5000
2. **Register**: Create a new account
3. **Login**: Sign in with your credentials
4. **Explore**: Navigate through the different pages
5. **Profile**: Update your profile information
6. **Settings**: View account settings and logout

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Support

If you encounter any issues or have questions:

1. Check the troubleshooting section above
2. Ensure all prerequisites are installed correctly
3. Verify MongoDB is running and accessible
4. Check the browser console for frontend errors
5. Check the server logs for backend errors

---
