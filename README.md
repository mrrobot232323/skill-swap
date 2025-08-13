# Skill Swap Platform

A full-stack web application where users can exchange skills with each other. Built with React, Node.js, Express, MongoDB, and Socket.IO for real-time chat functionality.
## 🚀 Features

### Core Features
- **User Authentication**: Secure JWT-based authentication with bcrypt password hashing
- **User Profiles**: Complete profile management with skills to teach and learn
- **Skill Listings**: Create, update, and manage skill offerings with detailed information
- **Smart Matching**: AI-powered algorithm to suggest skill exchanges between users
- **Real-time Chat**: Socket.IO powered messaging system with typing indicators
- **Search & Filters**: Advanced search functionality with multiple filter options
- **Admin Panel**: Comprehensive admin interface for platform management

### Technical Features
- **Frontend**: React.js with Vite, Tailwind CSS, React Router
- **Backend**: Node.js, Express.js, MongoDB with Mongoose
- **Real-time**: Socket.IO for live chat and notifications
- **Security**: Helmet.js, rate limiting, input validation
- **API Documentation**: Swagger/OpenAPI documentation

## 🛠️ Tech Stack

### Frontend
- React 18
- Vite
- Tailwind CSS
- React Router DOM
- Axios
- Socket.IO Client
- React Hook Form
- React Hot Toast
- Lucide React Icons

### Backend
- Node.js
- Express.js
- MongoDB
- Mongoose ODM
- Socket.IO
- JWT Authentication
- bcryptjs
- express-validator
- Helmet.js
- CORS

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- Node.js (v16 or higher)
- MongoDB (v4.4 or higher)
- npm or yarn

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd skillswap
```

### 2. Install Dependencies

```bash
# Install root dependencies
npm install

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

### 3. Environment Configuration

Create environment files for the backend:

```bash
cd backend
cp env.example .env
```

Edit the `.env` file with your configuration:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Configuration
MONGODB_URI=mongodb://localhost:27017/skillswap

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
JWT_EXPIRE=7d

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:3000

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
```

### 4. Database Setup

Make sure MongoDB is running on your system, then seed the database with sample data:

```bash
cd backend
npm run seed
```

This will create sample users, skills, and matches for testing.

### 5. Start the Application

#### Development Mode (Recommended)

From the root directory:

```bash
npm run dev
```

This will start both the backend (port 5000) and frontend (port 3000) concurrently.

#### Production Mode

```bash
# Build the frontend
cd frontend
npm run build

# Start the backend
cd ../backend
npm start
```

## 🎯 Usage

### Demo Accounts

The seed script creates several demo accounts:

- **Regular User**: `john@example.com` / `password123`
- **Admin User**: `admin@skillswap.com` / `admin123`

### Key Features Walkthrough

1. **Registration/Login**: Create an account or use demo credentials
2. **Profile Setup**: Add skills you can teach and want to learn
3. **Create Skills**: List your skills with detailed descriptions
4. **Find Matches**: Browse suggested skill exchanges
5. **Chat**: Communicate with matched users in real-time
6. **Search**: Find specific skills or users

## 📁 Project Structure

```
skillswap/
├── backend/                 # Backend API
│   ├── models/             # MongoDB schemas
│   ├── routes/             # API routes
│   ├── middleware/         # Custom middleware
│   ├── utils/              # Utility functions
│   ├── socket/             # Socket.IO handlers
│   ├── scripts/            # Database seeding
│   └── server.js           # Main server file
├── frontend/               # React frontend
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── pages/          # Page components
│   │   ├── contexts/       # React contexts
│   │   ├── services/       # API services
│   │   └── App.jsx         # Main app component
│   └── public/             # Static assets
└── README.md
```

## 🔧 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Get current user

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/profile` - Update profile
- `GET /api/users/search` - Search users

### Skills
- `GET /api/skills` - Get all skills with filters
- `POST /api/skills` - Create new skill
- `GET /api/skills/:id` - Get skill details
- `PUT /api/skills/:id` - Update skill
- `DELETE /api/skills/:id` - Delete skill

### Matches
- `GET /api/matches` - Get user matches
- `POST /api/matches` - Create match
- `PUT /api/matches/:id/respond` - Accept/reject match
- `GET /api/matches/suggestions` - Get match suggestions

### Messages
- `GET /api/messages/conversations` - Get conversations
- `GET /api/messages/:userId` - Get messages with user
- `POST /api/messages` - Send message

### Admin (Admin only)
- `GET /api/admin/users` - Get all users
- `GET /api/admin/stats` - Platform statistics
- `PUT /api/admin/users/:id/ban` - Ban/unban user

## 🔒 Security Features

- JWT authentication with HttpOnly cookies
- Password hashing with bcrypt
- Input validation with express-validator
- Rate limiting on auth routes
- Helmet.js for security headers
- CORS configuration
- MongoDB injection protection

## 🚀 Deployment

### Backend Deployment

1. Set up a MongoDB database (MongoDB Atlas recommended)
2. Configure environment variables for production
3. Deploy to platforms like Heroku, Railway, or DigitalOcean

### Frontend Deployment

1. Build the application: `npm run build`
2. Deploy the `dist` folder to platforms like Vercel, Netlify, or AWS S3

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License.

## 🆘 Support

For support and questions:
- Create an issue in the repository
- Check the API documentation
- Review the code comments

## 🎉 Acknowledgments

- React team for the amazing framework
- Tailwind CSS for the utility-first styling
- Socket.IO for real-time functionality
- MongoDB for the flexible database solution

