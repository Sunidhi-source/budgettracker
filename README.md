# Budget Tracker 💰

A full-stack expense and income tracking application built with the MERN stack. Track your financial transactions, visualize spending patterns, and manage your budget effectively.

![Budget Tracker](screenshots/dashboard.png)

---

## ✨ Features

- **User Authentication**
  - Secure sign-up and login with JWT
  - Password encryption with bcryptjs
  - User profile management

- **Income Tracking**
  - Add and manage income sources
  - Track income by category/source
  - Real-time balance updates

- **Expense Tracking**
  - Log expenses with categories and dates
  - Add descriptions and custom emojis
  - Visual expense organization

- **Dashboard Analytics**
  - Total balance overview
  - Income vs. expense comparison
  - Recent transactions list
  - Finance overview with interactive pie charts
  - Last 30 days expenses visualization
  - Real-time financial metrics

- **Data Visualization**
  - Line charts for financial trends
  - Pie charts for expense/income distribution
  - Bar charts for comparative analysis
  - Custom chart components with legends and tooltips

- **File Management**
  - Profile photo uploads
  - Excel export capabilities for financial reports
  - Secure file handling with multer

---

## 📊 Screenshots

### Dashboard
![Dashboard View](screenshots/dashboard-main.png)
*Main dashboard showing total balance, income, expenses, and recent transactions*

### Sign Up
![Sign Up Page](screenshots/signup.png)
*New account creation with profile photo upload*

### Empty State
![Empty State](screenshots/empty-state.png)
*User-friendly empty state when no transactions exist*

---

## 🛠 Technology Stack

### Frontend
- **Framework**: React 19
- **Build Tool**: Vite
- **Styling**: TailwindCSS 4
- **Charts**: Recharts
- **HTTP Client**: Axios
- **Routing**: React Router DOM 7
- **UI Features**: 
  - Emoji Picker
  - React Hot Toast (Notifications)
  - React Icons
- **Linting**: ESLint

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js 5
- **Database**: MongoDB with Mongoose
- **Authentication**: JWT (jsonwebtoken)
- **Password Security**: bcryptjs
- **File Upload**: Multer
- **Data Export**: XLSX
- **Environment**: dotenv
- **Development**: Nodemon

---

## 📁 Project Structure

```
budget-tracker/
├── Frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Cards/              # Reusable card components
│   │   │   ├── Charts/             # Chart visualizations
│   │   │   ├── Dashboard/          # Dashboard components
│   │   │   ├── Expense/            # Expense-related components
│   │   │   ├── Income/             # Income-related components
│   │   │   ├── Inputs/             # Input field components
│   │   │   └── layouts/            # Page layouts
│   │   ├── pages/
│   │   │   ├── Auth/               # Login and Sign-up pages
│   │   │   └── Dashboard/          # Dashboard pages
│   │   ├── context/                # React Context (User state)
│   │   ├── hooks/                  # Custom React hooks
│   │   └── utils/                  # Helper functions
│   ├── package.json
│   ├── vite.config.js
│   └── index.html
│
├── Backend/
│   ├── config/
│   │   └── db.js                   # MongoDB connection
│   ├── controllers/
│   │   ├── authController.js       # Auth logic
│   │   ├── dashboardController.js  # Dashboard stats
│   │   ├── expenseController.js    # Expense CRUD
│   │   └── incomeController.js     # Income CRUD
│   ├── middleware/
│   │   ├── authMiddleware.js       # JWT verification
│   │   └── uploadMiddleware.js     # File upload config
│   ├── models/
│   │   ├── User.js                 # User schema
│   │   ├── Expense.js              # Expense schema
│   │   └── Income.js               # Income schema
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── dashboardRoutes.js
│   │   ├── expenseRoutes.js
│   │   └── incomeRoutes.js
│   ├── server.js
│   ├── package.json
│   └── .env
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- MongoDB Atlas account or local MongoDB installation

### Installation

#### 1. Clone the Repository
```bash
git clone <repository-url>
cd budget-tracker
```

#### 2. Backend Setup

```bash
cd Backend
npm install
```

Create a `.env` file in the Backend directory:
```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=5000
FRONTEND_URL=http://localhost:5173
```

#### 3. Frontend Setup

```bash
cd ../Frontend
npm install
```

### 🏃 Running the Application

#### Development Mode

**Terminal 1 - Backend:**
```bash
cd Backend
npm run dev
```
Server runs on `http://localhost:5000`

**Terminal 2 - Frontend:**
```bash
cd Frontend
npm run dev
```
Application runs on `http://localhost:5173`

#### Production Build

**Backend:**
```bash
cd Backend
npm start
```

**Frontend:**
```bash
cd Frontend
npm run build
npm run preview
```

---

## 📡 API Routes

### Authentication Routes (`/api/auth`)
- `POST /signup` - Register new user
- `POST /login` - User login
- `POST /logout` - User logout

### Dashboard Routes (`/api/dashboard`)
- `GET /stats` - Get financial summary (balance, income, expenses)
- `GET /recent-transactions` - Get recent transactions

### Income Routes (`/api/income`)
- `GET /` - Get all income entries
- `POST /` - Create new income entry
- `PUT /:id` - Update income entry
- `DELETE /:id` - Delete income entry

### Expense Routes (`/api/expense`)
- `GET /` - Get all expense entries
- `POST /` - Create new expense entry
- `PUT /:id` - Update expense entry
- `DELETE /:id` - Delete expense entry

---

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for secure authentication:
- Tokens are stored in HTTP-only cookies
- Password is hashed using bcryptjs before storage
- Protected routes require valid JWT token
- Automatic token verification via middleware

---

## 💾 Database Schema

### User
```javascript
{
  name: String,
  email: String (unique),
  password: String (hashed),
  profilePhoto: String (URL),
  createdAt: Date
}
```

### Income
```javascript
{
  userId: ObjectId,
  source: String,
  amount: Number,
  description: String,
  emoji: String,
  date: Date,
  createdAt: Date
}
```

### Expense
```javascript
{
  userId: ObjectId,
  category: String,
  amount: Number,
  description: String,
  emoji: String,
  date: Date,
  createdAt: Date
}
```

---

## 🎨 Features Breakdown

### Dashboard
- Real-time balance calculation
- Income and expense summary cards
- Recent transactions with emoji indicators
- Interactive pie chart showing balance distribution
- Responsive grid layout

### Expense Management
- Add expenses with category and date
- View expense list with filtering
- Edit and delete expenses
- Visual expense overview
- Monthly expense trends

### Income Management
- Track income from multiple sources
- Income breakdown chart
- Recent income display
- Income trends visualization

### User Profile
- Profile photo upload
- User information display
- Account settings

---

## 📱 Responsive Design

The application is fully responsive and works seamlessly on:
- Desktop computers (1920px and up)
- Tablets (768px to 1024px)
- Mobile devices (320px to 767px)

Built with TailwindCSS for modern, mobile-first styling.

---

## 🐛 Error Handling

- Comprehensive error messages
- Input validation on both frontend and backend
- Graceful error recovery
- User notifications via toast messages

---

## 📈 Future Enhancements

- [ ] Budget goals and alerts
- [ ] Recurring transactions
- [ ] Multi-currency support
- [ ] Data export to PDF
- [ ] Budget comparison by category
- [ ] Mobile app (React Native)
- [ ] Dark mode

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the ISC License - see the LICENSE file for details.

---

## 👤 Author

**Sunidhi**

---

## ❓ Support

For support, email [your-email@example.com](mailto:your-email@example.com) or open an issue in the repository.

---

## 🔗 Links

- [Live Demo](#) - Coming soon
- [Backend Repository](#)
- [Frontend Repository](#)

---

**Happy tracking! 💸📊**
