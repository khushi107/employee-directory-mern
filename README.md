# 👥 Employee Directory - MERN Stack Application

A full-stack employee management system built with MongoDB, Express.js, React, and Node.js.

## 🚀 Features

- **Employee Management**: Add, edit, view, and delete employees
- **Search & Filter**: Search by name/email and filter by department
- **Undo Delete**: 5-second window to undo employee deletion
- **Toast Notifications**: Real-time feedback for all actions
- **Responsive Design**: Works seamlessly on desktop and mobile
- **REST API**: Complete backend API with validation

## 📋 Table of Contents

- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Screenshots](#screenshots)
- [Author](#author)

## 🛠️ Tech Stack

### Frontend
- React 18
- Axios for API calls
- CSS3 for styling
- Responsive design

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- CORS enabled

## 📁 Project Structure

```
employee-directory/
├── employee-directory-backend/    # Backend API
│   ├── config/
│   │   └── db.js                 # Database configuration
│   ├── controllers/
│   │   └── employeeController.js # Business logic
│   ├── models/
│   │   └── Employee.js           # Mongoose schema
│   ├── routes/
│   │   └── employeeRoutes.js     # API routes
│   ├── middleware/
│   │   └── errorHandler.js       # Error handling
│   ├── .env                       # Environment variables
│   ├── server.js                  # Entry point
│   └── package.json
│
└── employee-directory/            # Frontend React App
    ├── src/
    │   ├── components/            # Reusable components
    │   │   ├── EmployeeCard.jsx
    │   │   ├── EmployeeForm.jsx
    │   │   ├── SearchBar.jsx
    │   │   ├── Toast.jsx
    │   │   └── UndoToast.jsx
    │   ├── pages/
    │   │   └── EmployeeList.jsx  # Main page
    │   ├── services/
    │   │   └── employeeService.js # API calls
    │   ├── utils/
    │   │   └── dummyData.js      # Test data
    │   ├── App.js
    │   └── index.js
    └── package.json
```

## 💻 Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or MongoDB Atlas account)
- npm or yarn

### Clone Repository
```bash
git clone https://github.com/yourusername/employee-directory.git
cd employee-directory
```

### Backend Setup

1. Navigate to backend folder:
```bash
cd employee-directory-backend
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/employee-directory
```

For MongoDB Atlas:
```env
PORT=5000
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/employee-directory
```

4. Start the backend server:
```bash
npm run dev
```

Server will run on `http://localhost:5000`

### Frontend Setup

1. Open new terminal and navigate to frontend folder:
```bash
cd employee-directory
```

2. Install dependencies:
```bash
npm install
```

3. Start the React app:
```bash
npm start
```

App will open at `http://localhost:3000`

## 🚀 Running the Application

### Development Mode

**Terminal 1 - Backend:**
```bash
cd employee-directory-backend
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd employee-directory
npm start
```

### Production Build

**Backend:**
```bash
npm start
```

**Frontend:**
```bash
npm run build
# Serve the build folder with a static server
```

## 📡 API Endpoints

Base URL: `http://localhost:5000/api/employees`

### Get All Employees
```
GET /api/employees
```

**Response:**
```json
{
  "success": true,
  "count": 5,
  "data": [...]
}
```

### Get Single Employee
```
GET /api/employees/:id
```

### Create Employee
```
POST /api/employees
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@company.com",
  "phone": "+1 (555) 123-4567",
  "department": "Engineering",
  "position": "Software Engineer",
  "joiningDate": "2024-01-15"
}
```

### Update Employee
```
PUT /api/employees/:id
Content-Type: application/json

{
  "name": "John Doe Updated",
  "position": "Senior Engineer"
}
```

### Delete Employee
```
DELETE /api/employees/:id
```

## 📸 Screenshots

### Employee List
![Employee List](screenshots/employee-list.png)

### Add/Edit Form
![Add Employee](screenshots/add-employee.png)

### Delete with Undo
![Delete Undo](screenshots/delete-undo.png)


![Delete Undo](screenshots/delete-undo1.png)

### Search Filter
![Search Filter](screenshots/search-filter.png)

## 🎯 Key Features Explained

### Search & Filter
- Real-time search by name or email
- Filter employees by department
- Shows "No results" when no matches found

### Delete with Undo
- Click delete → Employee removed from UI
- 5-second countdown to undo
- Click "Undo" to restore employee
- After 5 seconds, permanently deleted from database

### Toast Notifications
- **Success** (Green): Add, edit, delete confirmations
- **Info** (Blue): Undo actions
- **Error** (Red): Validation or server errors
- Auto-dismiss after 3 seconds

### Form Validation
- Required fields: Name, Email, Department, Position
- Email format validation
- Duplicate email detection
- Real-time error messages

## 🔒 Environment Variables

### Backend (.env)
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
```

⚠️ **Never commit `.env` file to GitHub**

## 🐛 Troubleshooting

### MongoDB Connection Error
```bash
# Start MongoDB service (Windows)
net start MongoDB

# Mac/Linux
brew services start mongodb-community
```

### CORS Error
- Ensure backend is running on port 5000
- Check `server.js` has `app.use(cors())`

### Port Already in Use
```bash
# Kill process on port 5000
npx kill-port 5000

# Kill process on port 3000
npx kill-port 3000
```

## 📚 Technologies Used

| Technology | Purpose |
|------------|---------|
| React | Frontend UI library |
| Express.js | Backend web framework |
| MongoDB | NoSQL database |
| Mongoose | MongoDB object modeling |
| Axios | HTTP client |
| Nodemon | Auto-restart server |
| CORS | Cross-origin resource sharing |


## 👨‍💻 Author

**Your Name**
- GitHub: https://github.com/khushi107
- Email: khushi85449@gmail.com
