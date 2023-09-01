# Backend API Documentation

Welcome to the documentation for the backend API of the Currency Conversion Application. This API provides various endpoints for user authentication, currency conversion, and exchange rate retrieval. The base URL for this API is `https://fair-jade-deer-tam.cyclic.cloud/`. It has been hosted using CYCLIC.

## Authentication Endpoints

### 1. POST /sign-up

**Description**: Create a new user account.

**Endpoint**: `/sign-up`

**Request Body**:
```json
{
  "username": "your_username",
  "password": "your_password"
}
```

**Response**: Returns a boolean value indicating if the user has signed up successfully.

### 2. POST /login

**Description**: Authenticate a user and receive a JWT token.

**Endpoint**: `/login`

**Request Body**:
```json
{
  "username": "your_username",
  "password": "your_password"
}
```

**Response**: Returns a JSON object containing a JWT token that can be used for subsequent authenticated requests.

## Currency Conversion Endpoints

### 1. GET /exchange-rates

**Description**: Retrieve exchange rates for currencies.

**Endpoint**: `/exchange-rates`

**Request Headers**:
- `authorization`: JWT token obtained from successful login

**Response**: Returns a JSON object containing exchange rates for various currencies.

### 2. POST /convert

**Description**: Convert an amount from one currency to another.

**Endpoint**: `/convert`

**Request Body**:
```json
{
  "currency1": "USD",
  "currency2": "EUR",
  "amount": 100
}
```

**Request Headers**:
- `authorization`: JWT token obtained from successful login

**Response**: Returns the converted amount from `currency1` to `currency2`.

### 3. POST /historical-conversion

**Description**: Retrieve historical conversion rates for the past 7 days.

**Endpoint**: `/historical-conversion`

**Request Body**:
```json
{
  "currency1": "USD",
  "currency2": "EUR"
}
```

**Request Headers**:
- `authorization`: JWT token obtained from successful login

**Response**: Returns historical conversion rates for `currency1` to `currency2` for the past 7 days.
