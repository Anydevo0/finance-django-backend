# API Documentation

This document provides an overview of the API endpoints for the `authentication` and `finance` apps. Each endpoint includes example requests and responses to assist frontend developers in integrating with the backend.

---

## Authentication Endpoints

### 1. User Login
**POST** `/authentication/login/`

**Description:** Authenticates a user and returns a token.

**Request Body:**
```json
{
  "username": "example_user",
  "password": "example_password"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 1,
    "username": "example_user",
    "email": "user@example.com"
  }
}
```

---

### 2. User Registration
**POST** `/authentication/register/`

**Description:** Registers a new user.

**Request Body:**
```json
{
  "username": "new_user",
  "email": "new_user@example.com",
  "password": "secure_password"
}
```

**Response:**
```json
{
  "id": 2,
  "username": "new_user",
  "email": "new_user@example.com"
}
```

---

### 3. User Profile
**GET** `/authentication/profile/`

**Description:** Retrieves the profile of the authenticated user.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "id": 1,
  "username": "example_user",
  "email": "user@example.com"
}
```

---

## Finance Endpoints

### 1. Create Transaction
**POST** `/finance/transactions/`

**Description:** Creates a new financial transaction.

**Request Body:**
```json
{
  "amount": 100.50,
  "category": "Groceries",
  "description": "Weekly grocery shopping",
  "date": "2025-09-01"
}
```

**Response:**
```json
{
  "id": 1,
  "amount": 100.50,
  "category": "Groceries",
  "description": "Weekly grocery shopping",
  "date": "2025-09-01",
  "created_at": "2025-09-02T10:00:00Z"
}
```

---

### 2. List Transactions
**GET** `/finance/transactions/`

**Description:** Retrieves a list of all transactions.

**Response:**
```json
[
  {
    "id": 1,
    "amount": 100.50,
    "category": "Groceries",
    "description": "Weekly grocery shopping",
    "date": "2025-09-01",
    "created_at": "2025-09-02T10:00:00Z"
  },
  {
    "id": 2,
    "amount": 50.00,
    "category": "Transportation",
    "description": "Gas refill",
    "date": "2025-09-01",
    "created_at": "2025-09-02T11:00:00Z"
  }
]
```

---

### 3. Transaction Details
**GET** `/finance/transactions/<id>/`

**Description:** Retrieves details of a specific transaction.

**Response:**
```json
{
  "id": 1,
  "amount": 100.50,
  "category": "Groceries",
  "description": "Weekly grocery shopping",
  "date": "2025-09-01",
  "created_at": "2025-09-02T10:00:00Z"
}
```

---

### 4. Update Transaction
**PUT** `/finance/transactions/<id>/`

**Description:** Updates an existing transaction.

**Request Body:**
```json
{
  "amount": 120.00,
  "category": "Groceries",
  "description": "Updated grocery shopping",
  "date": "2025-09-01"
}
```

**Response:**
```json
{
  "id": 1,
  "amount": 120.00,
  "category": "Groceries",
  "description": "Updated grocery shopping",
  "date": "2025-09-01",
  "created_at": "2025-09-02T10:00:00Z"
}
```

---

### 5. Delete Transaction
**DELETE** `/finance/transactions/<id>/`

**Description:** Deletes a specific transaction.

**Response:**
```json
{
  "message": "Transaction deleted successfully."
}
```

---

### 6. Create Category
**POST** `/finance/categories/`

**Description:** Creates a new category for transactions.

**Request Body:**
```json
{
  "name": "Groceries",
  "description": "Expenses related to grocery shopping"
}
```

**Response:**
```json
{
  "id": 1,
  "name": "Groceries",
  "description": "Expenses related to grocery shopping",
  "created_at": "2025-09-02T10:00:00Z"
}
```

---

### 7. List Categories
**GET** `/finance/categories/`

**Description:** Retrieves a list of all categories.

**Response:**
```json
[
  {
    "id": 1,
    "name": "Groceries",
    "description": "Expenses related to grocery shopping",
    "created_at": "2025-09-02T10:00:00Z"
  },
  {
    "id": 2,
    "name": "Transportation",
    "description": "Expenses related to travel and commuting",
    "created_at": "2025-09-02T11:00:00Z"
  }
]
```

---

### 8. Category Details
**GET** `/finance/categories/<id>/`

**Description:** Retrieves details of a specific category.

**Response:**
```json
{
  "id": 1,
  "name": "Groceries",
  "description": "Expenses related to grocery shopping",
  "created_at": "2025-09-02T10:00:00Z"
}
```

---

### 9. Update Category
**PUT** `/finance/categories/<id>/`

**Description:** Updates an existing category.

**Request Body:**
```json
{
  "name": "Updated Groceries",
  "description": "Updated description for grocery shopping"
}
```

**Response:**
```json
{
  "id": 1,
  "name": "Updated Groceries",
  "description": "Updated description for grocery shopping",
  "created_at": "2025-09-02T10:00:00Z"
}
```

---

### 10. Delete Category
**DELETE** `/finance/categories/<id>/`

**Description:** Deletes a specific category.

**Response:**
```json
{
  "message": "Category deleted successfully."
}
```

---

Feel free to reach out for any clarifications or additional examples.
