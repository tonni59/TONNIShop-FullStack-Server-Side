# TONNIShop Backend (Express + MongoDB)

This repository contains the backend server for the TONNIShop frontend project you provided.
It is a Node.js + Express application using MongoDB (Mongoose) for data storage.

## Features
- JWT authentication (login / register)
- User profile (view / update)
- Products CRUD (admin-protected create/update/delete)
- Orders (create, get by id, list current user's orders)
- Image upload (multipart/form-data, stores under `/uploads`)
- Seed script to populate sample data

## Files & Structure
```
/config
  db.js
/controllers
  authController.js
  productController.js
  orderController.js
  userController.js
/middleware
  authMiddleware.js
  errorMiddleware.js
/models
  User.js
  Product.js
  Order.js
/routes
  authRoutes.js
  userRoutes.js
  productRoutes.js
  orderRoutes.js
  uploadRoutes.js
/data
  seed.js
server.js
package.json
.env.example
uploads/ (image uploads)
```

## Quick start

### 🔑Default Credentials
- **Admin Email:** admin@example.com  
- **Password:** password

## ✨ Features & Functionality
- 👤 User authentication (JWT) & role-based access.
- 🛍 Product listing, searching, filtering, and management.
- 🛒 Shopping cart functionality with quantity updates.
- 📦 Order creation & history tracking.
- 📤 Image uploads stored in uploads/.
- 📱 Responsive frontend UI.

## 📊 Data Handling
- ✅MongoDB database for users, products, and orders
- ✅Mongoose schemas for structured data modeling
- ✅REST APIs for handling client requests

## 🧠 User Experience & Design
- ✅Intuitive product browsing and filtering
- ✅Responsive layout using modern design principles
- ✅Interactive cart and checkout pages

## 🔐 Authentication & Security
- ✅JSON Web Tokens (JWT) for authentication
- ✅bcrypt for password encryption
- ✅Protected routes for admin and user roles

## 🛠 Tech Stack
### Frontend
- [React.js](https://react.dev/) – UI library
- [Redux Toolkit](https://redux-toolkit.js.org/) – State management
- [Axios](https://axios-http.com/) – HTTP requests
- [React Router](https://reactrouter.com/) – Client-side routing
- [Bootstrap](https://getbootstrap.com/) / [Tailwind CSS](https://tailwindcss.com/) – Styling

### Backend
- [Node.js](https://nodejs.org/) – Runtime environment
- [Express.js](https://expressjs.com/) – Web framework
- [MongoDB](https://www.mongodb.com/) – Database
- [Mongoose](https://mongoosejs.com/) – ODM for MongoDB
- [bcrypt.js](https://github.com/dcodeIO/bcrypt.js) – Password hashing
- [jsonwebtoken (JWT)](https://jwt.io/) – Authentication
- [Multer](https://github.com/expressjs/multer) – File upload middleware
- [dotenv](https://github.com/motdotla/dotenv) – Environment variables

## 📂Repositories
- **Frontend Repo:** [Client Side](https://github.com/tonni59/QuickCart-Client-Side)  
- **Backend Repo:** [Server Side](https://github.com/tonni59/QuickCart-Server-Side)

---

## ⚙️ Setup & Installation

### 🛠 Client Setup
1. Clone the client repository:
   ```bash
   git clone https://github.com/tonni59/QuickCart-Client-Side.git
   cd QuickCart-Client-Side
    ```
2. Install dependencies:
   ```bash
    npm install
   ```
3. Create a .env file in the root and add:
   ```bash
         # ==========================
      # 🌐 API Config
    # ==========================
    VITE_API_URL=http://localhost:5000/api

    # ==========================
    # 💳 Payment Gateway (Public Keys Only)
    # ==========================
    VITE_STRIPE_PUBLIC_KEY=your_stripe_public_key
    VITE_PAYPAL_CLIENT_ID=your_paypal_client_id

    # ==========================
    # 🔑 Firebase (if used for Auth/Storage)
    # ==========================
    VITE_FIREBASE_API_KEY=your_firebase_api_key
    VITE_FIREBASE_AUTH_DOMAIN=your_firebase_auth_domain
    VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
    VITE_FIREBASE_STORAGE_BUCKET=your_firebase_storage_bucket
    VITE_FIREBASE_MESSAGING_SENDER_ID=your_firebase_messaging_id
    VITE_FIREBASE_APP_ID=your_firebase_app_id

    # ==========================
    # 📊 Analytics / Monitoring
    # ==========================
    VITE_GA_TRACKING_ID=your_google_analytics_tracking_id
 
   ```
4. Start development server:
   ```bash
   npm start
   ```

### 🖥️ Server Setup
1. Clone the server repository:
   ```bash
   git clone https://github.com/tonni59/QuickCart-Server-Side.git
   cd QuickCart-Server-Side
    ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a .env file in the root and add:
   ```bash
    # ==========================
    # 🔧 Server & Database
    # ==========================
     PORT=5000
    NODE_ENV=development
    MONGO_URI=your_mongodb_connection_string

    # ==========================
    # 🔐 Authentication & Security
    # ==========================
    JWT_SECRET=your_jwt_secret
    JWT_EXPIRES_IN=7d
    COOKIE_SECRET=your_cookie_secret

    # ==========================
    # 🌐 Client Config
    # ==========================
    CLIENT_URL=http://localhost:3000

     # ==========================
     # 💳 Payment Gateways
     # ==========================
    STRIPE_SECRET_KEY=your_stripe_secret_key
    PAYPAL_CLIENT_ID=your_paypal_client_id
    PAYPAL_CLIENT_SECRET=your_paypal_client_secret

    # ==========================
    # 📧 Email / Notifications
    # ==========================
    SMTP_HOST=smtp.yourmail.com
    SMTP_PORT=587
    SMTP_USER=your_email@example.com
    SMTP_PASS=your_email_password
    EMAIL_FROM=no-reply@yourdomain.com

    # ==========================
    # ☁️ Cloud Storage (e.g., Cloudinary, AWS S3)
    # ==========================
    CLOUDINARY_CLOUD_NAME=your_cloudinary_name
    CLOUDINARY_API_KEY=your_cloudinary_api_key
    CLOUDINARY_API_SECRET=your_cloudinary_api_secret

    # ==========================
    # 🔑 Third-Party Auth Integrations
    # ==========================
    GOOGLE_CLIENT_ID=your_google_oauth_client_id
    GOOGLE_CLIENT_SECRET=your_google_oauth_client_secret
    FACEBOOK_APP_ID=your_facebook_app_id
    FACEBOOK_APP_SECRET=your_facebook_app_secret

    # ==========================
    # 📊 Analytics / Monitoring
    # ==========================
    SENTRY_DSN=your_sentry_error_tracking_dsn

    # ==========================
    # ⚡ Caching / Performance
    # ==========================
   REDIS_URI=redis://localhost:6379


   ```
4. Start the server:
   ```bash
   npm run dev

   ```

## 📦 NPM Dependencies

```json
{
  "dependencies": {
    "@tanstack/react-query": "^5.64.2",
    "axios": "^1.7.9",
    "firebase": "^11.1.0",
    "react": "^18.3.1",
    "react-dom": "^18.3.1",
    "react-helmet-async": "^2.0.5",
    "react-hook-form": "^7.54.2",
    "react-icons": "^5.4.0",
    "react-modal": "^3.16.3",
    "react-rating": "^2.0.5",
    "react-rating-stars-component": "^2.2.0",
    "react-responsive-carousel": "^3.2.23",
    "react-router-dom": "^7.1.1",
    "react-toastify": "^11.0.3",
    "sort-by": "^1.2.0",
    "sweetalert2": "^11.15.10",
    "swiper": "^11.2.1"
  },
  "devDependencies": {
    "@vitejs/plugin-react": "^4.3.4",
    "autoprefixer": "^10.4.20",
    "daisyui": "^4.12.23",
    "eslint": "^9.17.0",
    "postcss": "^8.5.0",
    "tailwindcss": "^3.4.17",
    "vite": "^6.0.5"
  }
}
```
using cloud storage for uploads (S3), add rate-limiting, input validation, and stronger security settings.




## 📡 API Documentation

The backend of QuickCart E-commerce Website is built with Node.js + Express + MongoDB and exposes a RESTful API for handling authentication, products, orders, and user management.

## 🔑 Authentication

## POST /api/users/login
## Login with email and password.

## Sample Request
```bash
   POST /api/users/login
   Content-Type: application/json

   {
     "email": "admin@example.com",
     "password": "password123"
   }

  ```
## Sample Response
```bash
   {
  "_id": "64fd0cddc82e19c88a5c9e123",
  "name": "John Doe",
  "email": "john@example.com",
  "isAdmin": false,
  "token": "jwt_token_here"
}

   ```

## 📦 Products

## GET/api/products
## Fetch all products.
## Sample Response
```bash
   [
  {
    "_id": "64fd0e23c82e19c88a5c9f12",
    "name": "iPhone 15",
    "brand": "Apple",
    "category": "Smartphones",
    "price": 1299,
    "countInStock": 15
  },
  {
    "_id": "64fd0e9ac82e19c88a5c9f22",
    "name": "Nike Air Max",
    "brand": "Nike",
    "category": "Shoes",
    "price": 199,
    "countInStock": 40
  }
]

 ```
## GET/api/products/:id
## Fetch a single product by ID.
## Sample Request
```bash
GET /api/products/64fd0e23c82e19c88a5c9f12

 ```
## Sample Response
```bash
   {
  "_id": "64fd0e23c82e19c88a5c9f12",
  "name": "iPhone 15",
  "brand": "Apple",
  "category": "Smartphones",
  "price": 1299,
  "countInStock": 15,
  "description": "Latest Apple smartphone with A17 chip"
}

 ```
## POST/api/products (Admin Only)
## Create a new product.
## Sample Request
```bash
 {
  "name": "MacBook Pro",
  "brand": "Apple",
  "category": "Laptops",
  "description": "M2 Pro Chip, 16GB RAM",
  "price": 2499,
  "countInStock": 5
}
```
## Sample Response
```bash
 {
  "_id": "64fd10aac82e19c88a5ca055",
  "name": "MacBook Pro",
  "brand": "Apple",
  "category": "Laptops",
  "description": "M2 Pro Chip, 16GB RAM",
  "price": 2499,
  "countInStock": 5,
  "user": "64fd0b9c82e19c88a5c9e999"
}
```
## PUT/api/products (Admin Only)
## Update an existing product.
## Sample Request
```bash
 PUT /api/products/64fd10aac82e19c88a5ca055
{
  "price": 2299,
  "countInStock": 8
}
```
## Sample Response
```bash
{
  "_id": "64fd10aac82e19c88a5ca055",
  "name": "MacBook Pro",
  "brand": "Apple",
  "category": "Laptops",
  "description": "M2 Pro Chip, 16GB RAM",
  "price": 2299,
  "countInStock": 8,
  "user": "64fd0b9c82e19c88a5c9e999"
}
```
## DELETE/api/products (Admin Only)
## Delete a product.
## Sample Request
```bash
 DELETE /api/products/64fd10aac82e19c88a5ca055
```
## Sample Response
```bash
{ "message": "Product removed" }
```
## 🛒 Orders

## POST /api/orders
## create a new order.

## Sample Request
```bash
  {
  "orderItems": [
    {
      "product": "64fd0e23c82e19c88a5c9f12",
      "qty": 2
    }
  ],
  "shippingAddress": {
    "address": "123 Street",
    "city": "Dhaka",
    "postalCode": "1212",
    "country": "Bangladesh"
  },
  "paymentMethod": "PayPal",
  "itemsPrice": 2598,
  "shippingPrice": 50,
  "totalPrice": 2648
}

  ```
## Sample Response
```bash
{
  "_id": "64fd125ac82e19c88a5ca199",
  "orderItems": [
    {
      "product": "64fd0e23c82e19c88a5c9f12",
      "qty": 2
    }
  ],
  "paymentMethod": "PayPal",
  "totalPrice": 2648,
  "isPaid": false,
  "isDelivered": false,
  "user": "64fd0cddc82e19c88a5c9e123"
}

   ```
