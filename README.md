# 🛒 E-commerce API

A RESTful API for an e-commerce system that allows users to manage products, handle authentication, and interact with a shopping cart.

## 📚 Table of Contents

- [Overview](#-overview)
- [Dependencies](#-dependencies)
- [Base URL](#-base-url)
- [Authentication](#-authentication)
- [Endpoints](#-endpoints)
  - [Auth](#auth)
  - [Products](#products)
  - [Cart](#cart)
- [Data Models](#-data-models)

---

## 📖 Overview

This API provides core functionalities for an e-commerce platform, including:

- User login/logout
- Product CRUD operations
- Product search
- Cart operations (add, remove, view, checkout)

---

## ⚙️ Dependencies

This project requires the following Python packages:

- Flask==2.3.0
- Flask-SQLAlchemy==3.1.1
- Flask-Login==0.6.2
- Flask-Cors==3.0.10
- Werkzeug==2.3.0

---

## 🌐 Base URL

http://127.0.0.1:5000

All endpoints listed below are relative to this base URL.

---

## 🔧 Endpoints

### 🔑 Auth

#### `POST /login`
Log in a user.

Request Body:
```json
{
  "username": "john_doe",
  "password": "secure_password"
}
```

#### `POST /logout`
Logs out the user.

### 📦 Products

#### `GET /api/products`
Retrieve all products.

#### `GET /api/products/{product_id}`
Get a product by ID.

#### `GET /api/products/search?q=...`
Search products by query string.

#### `POST /api/products/add`
Add a new product.

Request Body:
```json
{
  "id": 1,
  "name": "T-Shirt",
  "price": 29.99,
  "description": "Cotton T-shirt"
}
```

#### `PUT /api/products/update/{product_id}`
Update an existing product.

#### `DELETE /api/products/delete/{product_id}`
Delete a product.

### 🛒 Cart

#### `POST /api/cart/add/{product_id}`
Add a product to the cart.

#### `DELETE /api/cart/remove/{item_id}`
Remove an item from the cart.

#### `GET /api/cart`
Get current user's cart contents.

#### `POST /api/cart/checkout`
Checkout and clear the cart.

## 🧾 Data Models

### 🧍 User
```json
{
  "id": 1,
  "username": "john_doe",
  "password": "hashed_password",
  "cart": [CartItem]
}
```

### 📦 Product
```json
{
  "id": 1,
  "name": "T-Shirt",
  "price": 29.99,
  "description": "Cotton T-shirt"
}
```

### 🛒 CartItem
```json
{
  "id": 1,
  "user_id": 1,
  "product_id": 1
}
```