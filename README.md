# 🛒 Ecommerce Backend API Documentation

## Overview
The **Ecommerce Backend API** provides a set of RESTful endpoints to manage products in an eCommerce application.  
It allows users to perform **CRUD operations** (Create, Read, Update, Delete) on products, supports **image uploads**, and **search functionality**.

The backend is built using **Spring Boot** and supports interactions via **HTTP requests**.

---

## 📍 Base URL
http://localhost:8080/api


---

## 🚀 Endpoints

### 1. Get All Products
- **Method:** GET
- **URL:** `/products`
- **Description:** Fetches all available products.
- **Success Status Code:** `200 OK`
- **Failure Status Code:** `500 Internal Server Error`

---

### 2. Get Product by ID
- **Method:** GET
- **URL:** `/product/{prodId}`
- **Description:** Fetches a product by its ID.
- **URL Parameter:**
  - `prodId`: ID of the product.
- **Success Status Code:** `200 OK`
- **Failure Status Code:** `404 Not Found`

---

### 3. Add New Product
- **Method:** POST
- **URL:** `/product`
- **Description:** Adds a new product to the database, optionally with an image.
- **Body Parameters (form-data):**
  - `product`: JSON object (example below)
    ```json
    {
      "name": "New Product",
      "description": "New product description",
      "price": 250.00
    }
    ```
  - `imageFile`: Upload image file (optional).
- **Success Status Code:** `201 Created`
- **Failure Status Code:** `500 Internal Server Error`

---

### 4. Get Product Image by ID
- **Method:** GET
- **URL:** `/product/{prodId}/image`
- **Description:** Fetches the image associated with a product.
- **URL Parameter:**
  - `prodId`: ID of the product.
- **Success Status Code:** `200 OK`
- **Failure Status Code:** `404 Not Found`

---

### 5. Update Product
- **Method:** PUT
- **URL:** `/product/{id}`
- **Description:** Updates an existing product's details and image.
- **URL Parameter:**
  - `id`: ID of the product.
- **Body Parameters (form-data):**
  - `product`: JSON object (example below)
    ```json
    {
      "name": "Updated Product",
      "description": "Updated description",
      "price": 300.00
    }
    ```
  - `imageFile`: Upload updated image file (optional).
- **Success Status Code:** `200 OK`
- **Failure Status Code:** `400 Bad Request`

---

### 6. Delete Product
- **Method:** DELETE
- **URL:** `/product/{id}`
- **Description:** Deletes a product by its ID.
- **URL Parameter:**
  - `id`: ID of the product.
- **Success Status Code:** `200 OK`
- **Failure Status Code:** `404 Not Found`

---

### 7. Search Products
- **Method:** GET
- **URL:** `/products/search`
- **Query Parameter:**
  - `keyword`: Search term to filter products.
- **Description:** Searches for products based on a given keyword.
- **Success Status Code:** `200 OK`
- **Failure Status Code:** `400 Bad Request`

**Example:**
http://localhost:8080/api/products/search?keyword=phone


---

## 🔒 Authentication
> This API currently **does not require authentication**.  
> Future updates may integrate authentication mechanisms (e.g., JWT tokens).

---

## ⚠️ Error Codes

| Code | Meaning                        |
|----- |-------------------------------- |
| 200  | OK (Request successful)         |
| 400  | Bad Request (Invalid parameters)|
| 404  | Not Found (Resource not found)  |
| 500  | Internal Server Error           |

---

## 📢 Conclusion
This API provides a robust foundation to manage products for an eCommerce platform.  
It supports basic product operations along with image management, and is designed to be **scalable** and **extensible** for future enhancements.

---

> ⭐ Feel free to test the API using Postman and customize it based on your application needs!
