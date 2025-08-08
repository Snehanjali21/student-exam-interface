# Exam Taking Interface

A full-stack exam-taking application built with React.js frontend and Node.js/Express backend with MongoDB database. This application provides a complete exam-taking experience with JWT authentication, randomized MCQ questions, countdown timer, and detailed results.

## Features

### 🔐 Authentication
- JWT-based user registration and login
- Secure password hashing with bcrypt
- Protected routes and API endpoints
- User profile management

### 📝 Exam Interface
- Randomized MCQ questions from backend
- Next/Previous navigation between questions
- Real-time countdown timer with auto-submit
- Progress tracking and question indicators
- Auto-save answers as you go

### ⏱️ Timer System
- 30-minute countdown timer
- Visual timer with color-coded warnings
- Auto-submit when time expires
- Prevents further interaction after timeout

### 📊 Results & Analytics
- Detailed exam results with percentage scores
- Question-by-question review with correct/incorrect indicators
- Exam history with performance statistics
- Average scores and best performance tracking

### 🎨 Modern UI/UX
- Responsive design for all devices
- Beautiful gradient backgrounds
- Smooth animations and transitions
- Intuitive navigation and user flow

## Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **bcryptjs** - Password hashing
- **express-validator** - Input validation
- **helmet** - Security middleware
- **cors** - Cross-origin resource sharing

### Frontend
- **React.js** - UI library
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **React Hot Toast** - Notifications
- **React Icons** - Icon library

## Project Structure

```
exam-taking-interface/
├── backend/
│   ├── models/
│   │   ├── User.js
│   │   ├── Question.js
│   │   └── Exam.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── exam.js
│   │   └── questions.js
│   ├── middleware/
│   │   └── auth.js
│   ├── server.js
│   ├── seed.js
│   ├── package.json
│   └── config.env
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── auth/
│   │   │   ├── exam/
│   │   │   ├── Dashboard.js
│   │   │   ├── Navbar.js
│   │   │   └── PrivateRoute.js
│   │   ├── contexts/
│   │   │   └── AuthContext.js
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
├── package.json
└── README.md
```

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud)
- npm or yarn

### 1. Clone the Repository
```bash
git clone <repository-url>
cd exam-taking-interface
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

### 3. Environment Setup

#### Backend Configuration
Create a `.env` file in the backend directory (or use the existing `config.env`):
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/exam_db
JWT_SECRET=your_jwt_secret_key_here_change_in_production
NODE_ENV=development
```

#### MongoDB Setup
1. Install MongoDB locally or use MongoDB Atlas
2. Create a database named `exam_db`
3. Update the `MONGODB_URI` in your environment file

### 4. Seed the Database
```bash
cd backend
node seed.js
```

This will create:
- Admin user: `admin@exam.com` / `admin123`
- Student user: `student@exam.com` / `student123`
- 15 sample questions across different categories

### 5. Start the Application

#### Development Mode (Both Frontend and Backend)
```bash
# From the root directory
npm run dev
```

#### Or Start Separately
```bash
# Start backend (from backend directory)
cd backend
npm run dev

# Start frontend (from frontend directory)
cd frontend
npm start
```

The application will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile
- `PUT /api/auth/profile` - Update user profile

### Exams
- `POST /api/exam/start` - Start a new exam
- `GET /api/exam/current` - Get current active exam
- `POST /api/exam/answer` - Submit answer for a question
- `POST /api/exam/submit` - Submit completed exam
- `GET /api/exam/history` - Get exam history
- `GET /api/exam/result/:examId` - Get specific exam result

### Questions (Admin Only)
- `GET /api/questions` - Get all questions
- `POST /api/questions` - Create new question
- `PUT /api/questions/:id` - Update question
- `DELETE /api/questions/:id` - Delete question
- `GET /api/questions/categories` - Get question categories

## Usage Guide

### For Students

1. **Registration/Login**
   - Register with email, username, and password
   - Or login with existing credentials

2. **Dashboard**
   - View exam statistics and performance
   - Choose exam category and difficulty
   - Start new exams

3. **Taking Exams**
   - Navigate through questions using Next/Previous
   - Monitor countdown timer
   - Submit answers automatically saved
   - Submit exam when finished

4. **Results & History**
   - View detailed exam results
   - Review correct/incorrect answers
   - Track performance over time

### For Administrators

1. **Question Management**
   - Add new questions with multiple choice options
   - Set correct answers and difficulty levels
   - Categorize questions by subject
   - Edit or delete existing questions

2. **User Management**
   - Monitor user registrations
   - View exam statistics
   - Manage user accounts

## Features in Detail

### JWT Authentication
- Secure token-based authentication
- Automatic token refresh
- Protected routes and API endpoints
- User session management

### Randomized Questions
- Questions randomly selected from database
- Filtered by category and difficulty
- Prevents question repetition
- Secure answer handling

### Timer System
- 30-minute countdown timer
- Visual progress indicator
- Color-coded warnings (green → yellow → red)
- Automatic exam submission on timeout

### Progress Tracking
- Real-time progress bar
- Question indicators showing answered/unanswered
- Navigation between questions
- Auto-save functionality

### Results & Analytics
- Percentage-based scoring
- Detailed performance metrics
- Question-by-question review
- Historical performance tracking

## Security Features

- **Password Hashing**: bcrypt with salt rounds
- **JWT Tokens**: Secure authentication
- **Input Validation**: Express-validator middleware
- **CORS Protection**: Cross-origin request handling
- **Rate Limiting**: API request throttling
- **Helmet**: Security headers
- **Environment Variables**: Secure configuration

## Deployment

### Backend Deployment
1. Set up MongoDB database (local or cloud)
2. Configure environment variables
3. Deploy to platforms like Heroku, Railway, or Vercel

### Frontend Deployment
1. Build the React app: `npm run build`
2. Deploy to platforms like Netlify, Vercel, or GitHub Pages
3. Update API endpoints for production

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request
