# Café Delight - Modern Café Website

A fully responsive, modern, animated café website with both frontend and backend functionality. Features online ordering, table reservations, job applications, and a comprehensive admin dashboard.

## Features

### Frontend
- Modern, premium café theme with warm colors
- Smooth animations (scroll animations, hover effects, fade-in sections)
- Fully responsive for mobile, tablet, and desktop
- Animated hero section with image slider
- Sticky navigation bar with smooth scrolling
- Attractive footer with social media links

### Pages
- **Home Page**: Hero banner, featured menu, about section, testimonials, location
- **Menu Page**: Categorized menu with search and filter functionality
- **Cart Page**: Shopping cart with checkout
- **Reservation Page**: Table booking system
- **Careers Page**: Job listings with application form

### Backend
- **Online Ordering System**: Add to cart, quantity control, checkout
- **WhatsApp Integration**: Floating WhatsApp button, order sharing
- **Table Reservation System**: Date/time selection, guest count
- **Careers System**: Job listings, application form with CV upload
- **Admin Dashboard**: Secure login, analytics, order/reservation management

## Technology Stack

### Frontend
- HTML5
- CSS3 (Custom CSS with CSS Variables)
- JavaScript (Vanilla JS)
- Font Awesome Icons
- Google Fonts

### Backend
- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT Authentication
- Multer (File Upload)
- Nodemailer (Email)

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Step 1: Clone the Repository
```bash
git clone <repository-url>
cd cafe-website
```

### Step 2: Install Dependencies
```bash
npm install
```

### Step 3: Configure Environment Variables
Create a `.env` file in the root directory:

```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/cafe_website
JWT_SECRET=your_super_secret_jwt_key_change_this_in_production
JWT_EXPIRE=7d

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password

# Admin Credentials
ADMIN_EMAIL=admin@cafe.com
ADMIN_PASSWORD=admin123

# WhatsApp Configuration
WHATSAPP_NUMBER=+1234567890

# App URL
APP_URL=http://localhost:3000
```

### Step 4: Seed the Database
```bash
npm run seed
```

This will create:
- Admin user (email: admin@cafe.com, password: admin123)
- Sample menu items
- Sample job listings

### Step 5: Start the Server

Development mode:
```bash
npm run dev
```

Production mode:
```bash
npm start
```

The website will be available at `http://localhost:3000`

## Project Structure

```
cafe-website/
├── models/                 # Database models
│   ├── User.js
│   ├── MenuItem.js
│   ├── Order.js
│   ├── Reservation.js
│   ├── Job.js
│   └── index.js
├── routes/                 # API routes
│   ├── auth.js
│   ├── menu.js
│   ├── orders.js
│   ├── reservations.js
│   ├── jobs.js
│   ├── admin.js
│   └── upload.js
├── middleware/             # Express middleware
│   └── auth.js
├── utils/                  # Utility functions
│   └── email.js
├── scripts/                # Database scripts
│   └── seed.js
├── public/                 # Static files
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   ├── main.js
│   │   ├── cart.js
│   │   ├── menu.js
│   │   ├── checkout.js
│   │   ├── reservation.js
│   │   └── careers.js
│   ├── index.html
│   ├── menu.html
│   ├── cart.html
│   ├── reservation.html
│   ├── careers.html
│   └── admin/
│       ├── login.html
│       └── dashboard.html
├── server.js               # Main server file
├── package.json
├── .env
└── README.md
```

## API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `POST /api/auth/register` - Register new user (Admin only)

### Menu
- `GET /api/menu` - Get all menu items
- `GET /api/menu/categories` - Get all categories
- `GET /api/menu/:id` - Get single menu item
- `POST /api/menu` - Create menu item (Admin)
- `PUT /api/menu/:id` - Update menu item (Admin)
- `DELETE /api/menu/:id` - Delete menu item (Admin)

### Orders
- `GET /api/orders` - Get all orders (Admin)
- `POST /api/orders` - Create new order
- `GET /api/orders/:id` - Get single order
- `PUT /api/orders/:id/status` - Update order status
- `GET /api/orders/stats/daily` - Get daily stats

### Reservations
- `GET /api/reservations` - Get all reservations (Admin)
- `POST /api/reservations` - Create new reservation
- `GET /api/reservations/:id` - Get single reservation
- `PUT /api/reservations/:id/status` - Update reservation status
- `PUT /api/reservations/:id/table` - Assign table number

### Jobs
- `GET /api/jobs` - Get all active jobs
- `GET /api/jobs/departments` - Get all departments
- `GET /api/jobs/:id` - Get single job
- `POST /api/jobs/:id/apply` - Submit job application
- `GET /api/jobs/admin/all` - Get all jobs (Admin)
- `POST /api/jobs` - Create job (Admin)
- `PUT /api/jobs/:id` - Update job (Admin)
- `DELETE /api/jobs/:id` - Delete job (Admin)

### Admin
- `GET /api/admin/dashboard` - Get dashboard stats
- `GET /api/admin/analytics` - Get detailed analytics

### Upload
- `POST /api/upload/image` - Upload image (Admin)
- `POST /api/upload/cv` - Upload CV

## Admin Dashboard

Access the admin dashboard at `/admin`

Default credentials:
- Email: admin@cafe.com
- Password: admin123

**Note**: Change these credentials in production!

## Deployment

### Deploy to Heroku

1. Create a Heroku account and install the Heroku CLI
2. Login to Heroku:
```bash
heroku login
```

3. Create a new Heroku app:
```bash
heroku create your-cafe-website
```

4. Set environment variables:
```bash
heroku config:set MONGODB_URI=your_mongodb_uri
heroku config:set JWT_SECRET=your_jwt_secret
heroku config:set ADMIN_EMAIL=admin@cafe.com
heroku config:set ADMIN_PASSWORD=your_secure_password
```

5. Deploy:
```bash
git push heroku main
```

### Deploy to VPS (Ubuntu)

1. Install Node.js and MongoDB on your server
2. Clone the repository
3. Install PM2:
```bash
npm install -g pm2
```

4. Start the application:
```bash
pm2 start server.js --name cafe-website
```

5. Configure Nginx as a reverse proxy

## Security Considerations

1. Change default admin credentials
2. Use strong JWT secret
3. Enable HTTPS in production
4. Set up proper CORS policies
5. Use environment variables for sensitive data
6. Implement rate limiting
7. Validate all user inputs

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

MIT License

## Support

For support, email hello@cafedelight.com or open an issue on GitHub.

## Credits

- Images from Unsplash
- Icons from Font Awesome
- Fonts from Google Fonts
