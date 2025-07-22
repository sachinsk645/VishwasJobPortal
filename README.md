# Vishwas Job Portal

A comprehensive full-stack job portal application with role-based authentication, modern UI, and advanced features for job seekers, recruiters, and administrators.

## 🚀 Features

### 🔐 Authentication & Authorization
- **JWT-based authentication** with secure token management
- **Role-based access control** (Admin, Recruiter, Applicant)
- **Protected routes** with automatic role-based redirection
- **Password hashing** with bcrypt
- **Session management** with HTTP-only cookies

### 👨‍💼 Admin Dashboard
- **User management** - View, activate/deactivate users
- **Job moderation** - Approve/reject job postings
- **Company verification** - Verify company profiles
- **Analytics & Reports** - User registrations, job postings, applications
- **System monitoring** - Dashboard with key metrics

### 🏢 Recruiter Dashboard
- **Company profile management** - Update company information
- **Job posting** - Create, edit, and manage job listings
- **Application management** - Review and manage applications
- **Candidate search** - Search candidates by skills and location
- **Interview scheduling** - Schedule and manage interviews

### 👩‍💼 Applicant Dashboard
- **Profile management** - Update personal information and resume
- **Job browsing** - Search and filter job opportunities
- **Application tracking** - Track application status
- **Job alerts** - Receive notifications for new opportunities
- **Saved jobs** - Bookmark interesting positions

### 🎨 Modern UI/UX
- **Responsive design** - Works on desktop, tablet, and mobile
- **Tailwind CSS** - Modern styling with custom components
- **Heroicons** - Beautiful iconography
- **Smooth animations** - Enhanced user experience
- **Dark/light mode ready** - Extensible theme system

### 🔧 Technical Features
- **Real-time notifications** - Application status updates
- **File upload** - Resume and profile picture upload
- **Search & filtering** - Advanced job and candidate search
- **Pagination** - Efficient data loading
- **Form validation** - Client and server-side validation

## 🛠️ Tech Stack

### Frontend
- **React.js** - Modern UI library
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **React Query** - Data fetching and caching
- **React Hook Form** - Form management
- **Axios** - HTTP client
- **React Hot Toast** - Toast notifications

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **MySQL** - Relational database
- **Sequelize** - ORM for database operations
- **JWT** - JSON Web Tokens for authentication
- **Bcrypt** - Password hashing
- **Multer** - File upload handling
- **Express Validator** - Input validation
- **Helmet** - Security middleware
- **CORS** - Cross-origin resource sharing

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Node.js** (v16 or higher)
- **MySQL** (v8.0 or higher)
- **npm** or **yarn**

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd vishwas-job-portal
```

### 2. Install Dependencies
```bash
# Install root dependencies
npm install

# Install all dependencies (frontend + backend)
npm run install-all
```

### 3. Database Setup
```bash
# Create MySQL database
mysql -u root -p
CREATE DATABASE vishwas_job_portal;
```

### 4. Environment Configuration
```bash
# Copy environment template
cp server/env.example server/.env

# Edit the .env file with your configuration
nano server/.env
```

**Required Environment Variables:**
```env
# Database Configuration
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=vishwas_job_portal
DB_PORT=3306

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRES_IN=7d

# Server Configuration
PORT=5000
NODE_ENV=development

# Email Configuration (optional)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password

# File Upload Configuration
UPLOAD_PATH=./uploads
MAX_FILE_SIZE=5242880
```

### 5. Database Migration
```bash
# Setup database tables
npm run setup-db
```

### 6. Start the Application
```bash
# Start both frontend and backend
npm run dev

# Or start individually
npm run server  # Backend only
npm run client  # Frontend only
```

The application will be available at:
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000

## 📁 Project Structure

```
vishwas-job-portal/
├── client/                 # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── contexts/       # React contexts
│   │   ├── pages/          # Page components
│   │   ├── hooks/          # Custom hooks
│   │   └── utils/          # Utility functions
│   └── package.json
├── server/                 # Node.js backend
│   ├── models/             # Database models
│   ├── routes/             # API routes
│   ├── middleware/         # Custom middleware
│   ├── uploads/            # File uploads
│   └── package.json
├── package.json
└── README.md
```

## 🔐 Default Users

After setup, you can create users through the registration page or directly in the database:

### Admin User
```sql
INSERT INTO users (email, password, firstName, lastName, role, isActive) 
VALUES ('admin@vishwas.com', '$2a$12$...', 'Admin', 'User', 'admin', true);
```

### Test Users
- **Recruiter**: recruiter@example.com / password123
- **Applicant**: applicant@example.com / password123

## 🚀 Deployment

### Frontend Deployment
```bash
# Build for production
cd client
npm run build

# Deploy to your hosting service (Netlify, Vercel, etc.)
```

### Backend Deployment
```bash
# Set NODE_ENV=production
# Configure production database
# Deploy to your server (Heroku, AWS, etc.)
```

## 🔧 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile
- `PUT /api/auth/profile` - Update profile
- `POST /api/auth/logout` - User logout

### Jobs
- `GET /api/jobs` - Get all jobs
- `GET /api/jobs/:id` - Get job details
- `POST /api/jobs` - Create job (recruiter)
- `PUT /api/jobs/:id` - Update job (recruiter)

### Applications
- `POST /api/applications` - Apply for job
- `GET /api/applications` - Get user applications
- `PUT /api/applications/:id/status` - Update application status

### Admin Routes
- `GET /api/admin/dashboard` - Admin dashboard
- `GET /api/admin/users` - Get all users
- `GET /api/admin/jobs` - Get all jobs
- `GET /api/admin/companies` - Get all companies

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/your-repo/issues) page
2. Create a new issue with detailed information
3. Contact the development team

## 🎯 Roadmap

- [ ] Email notifications
- [ ] Resume parsing
- [ ] Interview scheduling
- [ ] Advanced analytics
- [ ] Mobile app
- [ ] Multi-language support
- [ ] Payment integration
- [ ] AI-powered job matching

---

**Built with ❤️ by the Vishwas Job Portal Team** 