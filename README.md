# IPO Web Application

A comprehensive web application for managing and tracking Initial Public Offerings (IPOs), built with React frontend and Node.js backend.

## 🚀 Features

### Frontend (React)
- **Modern UI/UX**: Responsive design with beautiful animations
- **Authentication**: User registration, login, and profile management
- **IPO Management**: Browse upcoming IPOs, view details, and track performance
- **Dashboard**: Portfolio overview, watchlist, and performance analytics
- **Real-time Updates**: Live data updates and notifications
- **Mobile Responsive**: Optimized for all device sizes

### Backend (Node.js/Express)
- **RESTful API**: Complete CRUD operations for IPOs and users
- **Authentication**: JWT-based authentication with bcrypt password hashing
- **Database**: PostgreSQL with Sequelize ORM
- **Security**: Helmet, CORS, rate limiting, and input validation
- **Error Handling**: Comprehensive error management and logging

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI framework
- **React Router** - Client-side routing
- **Framer Motion** - Animations
- **Chart.js** - Data visualization
- **CSS3** - Styling with modern features

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **PostgreSQL** - Database
- **Sequelize** - ORM
- **JWT** - Authentication
- **bcryptjs** - Password hashing
- **express-validator** - Input validation

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **PostgreSQL** (v12 or higher)
- **Git**

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ipo-web-application
   ```

2. **Install dependencies**
   ```bash
   # Install root dependencies
   npm install
   
   # Install server dependencies
   cd server && npm install
   
   # Install client dependencies
   cd ../client && npm install
   ```

3. **Set up the database**
   ```bash
   # Create PostgreSQL database
   createdb ipo_web_app
   ```

4. **Configure environment variables**
   ```bash
   # Copy environment example file
   cd server
   cp env.example .env
   
   # Edit .env file with your configuration
   nano .env
   ```

5. **Start the application**
   ```bash
   # From the root directory
   npm run dev
   ```

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the `server` directory with the following variables:

```env
# Server Configuration
NODE_ENV=development
PORT=5000

# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_NAME=ipo_web_app
DB_USER=postgres
DB_PASSWORD=your_password
DB_DIALECT=postgres

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here_make_it_long_and_random
JWT_EXPIRES_IN=7d

# Client Configuration
CLIENT_URL=http://localhost:3000
```

## 📁 Project Structure

```
ipo-web-application/
├── client/                 # React frontend
│   ├── public/            # Static files
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── App.js         # Main app component
│   │   └── index.js       # Entry point
│   └── package.json
├── server/                # Node.js backend
│   ├── config/           # Configuration files
│   ├── middleware/       # Custom middleware
│   ├── models/           # Database models
│   ├── routes/           # API routes
│   ├── index.js          # Server entry point
│   └── package.json
├── package.json          # Root package.json
└── README.md
```

## 🎯 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Get current user profile
- `POST /api/auth/forgot-password` - Password reset request
- `POST /api/auth/reset-password` - Reset password

### IPOs
- `GET /api/ipos` - Get all IPOs with filtering
- `GET /api/ipos/upcoming` - Get upcoming IPOs
- `GET /api/ipos/:id` - Get IPO details
- `POST /api/ipos` - Create new IPO (Admin)
- `PUT /api/ipos/:id` - Update IPO (Admin)
- `DELETE /api/ipos/:id` - Delete IPO (Admin)
- `GET /api/ipos/sectors` - Get available sectors

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `PUT /api/users/password` - Change password
- `DELETE /api/users/account` - Delete account
- `GET /api/users/activity` - Get user activity
- `GET /api/users/preferences` - Get user preferences

### Dashboard
- `GET /api/dashboard/overview` - Dashboard overview
- `GET /api/dashboard/portfolio` - Portfolio data
- `GET /api/dashboard/watchlist` - User watchlist
- `POST /api/dashboard/watchlist` - Add to watchlist
- `DELETE /api/dashboard/watchlist/:ipoId` - Remove from watchlist
- `GET /api/dashboard/performance` - Performance data

## 🏃‍♂️ Running the Application

### Development Mode
```bash
# Start both frontend and backend
npm run dev

# Or start individually
npm run server  # Backend only
npm run client  # Frontend only
```

### Production Mode
```bash
# Build the frontend
npm run build

# Start the server
npm start
```

## 🧪 Testing

```bash
# Run backend tests
cd server && npm test

# Run frontend tests (when implemented)
cd client && npm test
```

## 📊 Database Schema

### Users Table
- `id` - Primary key
- `email` - Unique email address
- `password` - Hashed password
- `firstName` - User's first name
- `lastName` - User's last name
- `phone` - Phone number
- `isActive` - Account status
- `isAdmin` - Admin privileges
- `emailVerified` - Email verification status
- `preferences` - User preferences (JSON)
- `createdAt` - Account creation date
- `updatedAt` - Last update date

### IPOs Table
- `id` - Primary key
- `companyName` - Company name
- `tickerSymbol` - Stock ticker
- `sector` - Industry sector
- `description` - Company description
- `openDate` - IPO opening date
- `closeDate` - IPO closing date
- `priceRange` - Price range (JSON)
- `totalShares` - Total shares offered
- `marketCap` - Market capitalization
- `status` - IPO status (upcoming/active/listed/closed)
- `logoUrl` - Company logo URL
- `prospectusUrl` - Prospectus URL
- `financials` - Financial data (JSON)
- `createdAt` - Creation date
- `updatedAt` - Last update date

## 🔒 Security Features

- **Password Hashing**: bcryptjs for secure password storage
- **JWT Authentication**: Secure token-based authentication
- **Input Validation**: Comprehensive request validation
- **Rate Limiting**: Protection against brute force attacks
- **CORS**: Cross-origin resource sharing configuration
- **Helmet**: Security headers
- **SQL Injection Protection**: Sequelize ORM with parameterized queries

## 🚀 Deployment

### Backend Deployment
1. Set up a PostgreSQL database
2. Configure environment variables
3. Install dependencies: `npm install`
4. Run database migrations
5. Start the server: `npm start`

### Frontend Deployment
1. Build the application: `npm run build`
2. Deploy the `build` folder to your hosting service
3. Configure environment variables for API endpoints

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Authors

- **Bluestock Fintech Intern** - Initial work

## 🙏 Acknowledgments

- React team for the amazing framework
- Express.js team for the web framework
- Sequelize team for the ORM
- All contributors and maintainers

## 📞 Support

For support and questions, please contact:
- Email: support@bluestockfintech.com
- Documentation: [Link to documentation]
- Issues: [GitHub Issues](https://github.com/your-repo/issues) 