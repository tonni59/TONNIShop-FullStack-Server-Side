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

1. Copy `.env.example` to `.env` and fill values:
   ```
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/tonnishop
   JWT_SECRET=your_jwt_secret_here
   CLIENT_URL=http://localhost:3000
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Run the server (development):
   ```
   npm run dev
   ```

4. Seed sample data (optional):
   ```
   npm run seed
   ```

## API Endpoints (summary)
- `POST /api/auth/register` - register
- `POST /api/auth/login` - login
- `GET /api/users/profile` - get current user (protected)
- `PUT /api/users/profile` - update current user (protected)
- `GET /api/products` - list products
- `GET /api/products/:id` - product details
- `POST /api/products` - create product (admin)
- `PUT /api/products/:id` - update product (admin)
- `DELETE /api/products/:id` - delete product (admin)
- `POST /api/orders` - create order (protected)
- `GET /api/orders/myorders` - list orders for current user (protected)
- `GET /api/orders/:id` - get order by id (protected)
- `POST /api/upload` - file upload (multipart, field 'image')

## Notes
- This backend is intentionally minimal and designed to be compatible with typical React frontends.
- Adjust/add fields or routes to match your frontend expectations.
- For production, consider using cloud storage for uploads (S3), add rate-limiting, input validation, and stronger security settings.

