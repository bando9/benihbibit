# Benihbibit

[Benihbibit](https://benihbibit.bandomega.com) Simple Ecommerce Platform for Unique Seeds & Plant Seedlings

Benihbibit is a modern, lightweight ecommerce application designed to showcase and sell unique plant seeds and seedlings.
This project is built as a portfolio-grade fullstack application, focusing on clean architecture, RESTful API design, and real-world ecommerce flows.

Live Demo: https://benihbibit.bandomega.com

## Links

- Website/Frontend: <https://benihbibit.bandomega.com>
  - Backend API: <https://benihbibit-api.bandomega.com>
- Repositories:
  - General: <https://github.com/bando9/benihbibit>
  - Backend API: <https://github.com/bando9/benihbibit-api>
  - Frontend Web: <https://github.com/bando9/benihbibit-web>
- Project Management: <https://linear.app/benihbibit>

Inspirations:

- <https://benihbunbun.com> - Singapore's premier nature destination housing five world-class wildlife parks

## Features

- Home page
  - Hero section
  - Products catalogue. Example: <https://benihbunbun.com>
- Product page
  - Image URL
  - SKU (stock keeping unit)
  - Name
  - Price
  - Description
  - Stock level / In stock or not
  - Add to Cart Form:
    - Quantity Input
    - Increment & Decrement Button
    - Add to Cart Submit Button
- Shopping Cart page
  - Product items to buy
    - Image, name, price, quantity, subtotal (price x quantity)
    - Remove item
    - Change quantity form
  - Link: continue shopping, go to products catalogue
  - Link: checkout
- Checkout page
  - Order summary
    - Product items to buy
    - Grand total of all product items to buy
- Place order / transaction is being processed

## UI Designs

- Figma: <https://www.figma.com/design/sQWAnk4QR9CkiMKlqht2RL/benihbibit---simple-Ecommerce>

## Backend REST API Endpoints

- Production: `https://benihbibit.bandomega.com`
- Local: `http://localhost:3000`

Priority:

| Endpoint           | HTTP  | Description         | Permission |
| ------------------ | ----- | ------------------- | ---------- |
| `/products`        | `GET` | Get all products    | Public     |
| `/products/{slug}` | `GET` | Get product by slug | Public     |

With Auth:

| Endpoint         | HTTP   | Description              | Permission    |
| ---------------- | ------ | ------------------------ | ------------- |
| `/users`         | `GET`  | Get all users            | Public        |
| `/users/{id}`    | `GET`  | Get user by id           | Public        |
| `/auth/register` | `POST` | Register new user        | Public        |
| `/auth/login`    | `POST` | Login user               | Public        |
| `/auth/me`       | `GET`  | Check authenticated user | Authenticated |
| `/auth/logout`   | `POST` | Logout user              | Authenticated |

Cart:

| Endpoint           | HTTP     | Description                    | Permission    |
| ------------------ | -------- | ------------------------------ | ------------- |
| `/cart`            | `GET`    | Get user's cart                | Authenticated |
| `/cart/items`      | `PUT`    | Add product & quantity to cart | Authenticated |
| `/cart/items/{id}` | `DELETE` | Delete product from cart       | Authenticated |
| `/cart/items/{id}` | `PATCH`  | Update product quantity        | Authenticated |

## Frontend Pages

Priority:

| Route             | Title                    |
| ----------------- | ------------------------ |
| `/`               | Home Page                |
| `/products`       | All Products Page        |
| `/products/:slug` | One Product by Slug Page |

With Auth:

| Route        | Title                   | Permission    |
| ------------ | ----------------------- | ------------- |
| `/register`  | Register Page           | Public        |
| `/login`     | Login Page              | Public        |
| `/dashboard` | Authenticated User Page | Authenticated |
| `/logout`    | Logout Page             | Authenticated |
| `/cart`      | Cart Page               | Authenticated |

## Data Structure

### Product

```json
{
  "id": "ULID123",
  "slug": "kalender-dudukan-kayu-custom-5-pcs",
  "name": "Kalender Dudukan Kayu Custom 5pcs",
  "sku": "BEN-KDKC-1",
  "price": 225000,
  "stockQuantity": 10,
  "imageUrl": "https://uploadcare.com/images/image.jpg",
  "description": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

### Add New Product

Request Body:

```json
{
  "name": "FLYER A5 PAMFLET SEED PAPER 10 pcs",
  "price": 15000,
  "sku": "AZ-TIGER-1",
  "stockQuantity": 10,
  "imageUrl": "https://uploadcare.com/images/image.jpg",
  "description": "..."
}
```

Response Body:

```json
{
  "id": "ULID234",
  "slug": "flyer-a5-pamflet-seed-paper-10-pcs",
  "name": "FLYER A5 PAMFLET SEED PAPER 10 pcs",
  "price": 15000,
  "sku": "BEN-FPSP-1",
  "stockQuantity": 10,
  "imageUrl": "https://uploadcare.com/images/image.jpg",
  "description": "..."
}
```
