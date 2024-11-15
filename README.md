

# 🔒 **SecureAuthSystem API Documentation**

**SecureAuthSystem** offers a secure and scalable authentication framework, enabling users to register, log in, reset their password or username, and more. The following documentation covers the available API endpoints and their usage.

---

## 📌 **API Endpoints**

### 1. **User Registration**

- **Endpoint:** `POST http://localhost:9090/auth/signup`
- **Description:** Registers a new user with their username, password, mobile number, and email.
  
#### **Request Body Example:**
```json
{
  "username": "kundansingh",
  "password": "Kundan*&^$@!!@#321",
  "mobileNumber": "7827843470",
  "email": "kundangetcode@gmail.com"
}
```

---

### 2. **Verify Signup OTP**

- **Endpoint:** `POST http://localhost:9090/auth/verify-signup-otp`
- **Description:** Verifies the OTP sent to the user's email during registration.
  
#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com",
  "otp": "5919"
}
```

---

### 3. **User Login (with Username)**

To log in using **username**, follow these steps:

1. **Send OTP to Mobile Number**

- **Endpoint:** `POST http://localhost:9090/auth/send-otp`
- **Description:** Sends an OTP to the user's registered mobile number based on their username.

#### **Request Body Example:**
```json
{
  "username": "Kundansingh",
  "password": "Kundan*&^$@!!@#321"
}
```

2. **Verify OTP**

- **Endpoint:** `POST http://localhost:9090/auth/verify-otp`
- **Description:** Verifies the OTP sent to the user's mobile number.

#### **Request Body Example:**
```json
{
  "mobileNumber": "7827843470",
  "otp": "9781"
}
```

---

### 4. **User Login (with Email)**

To log in using **email**, follow these steps:

1. **Send OTP to Email**

- **Endpoint:** `POST http://localhost:9090/auth/login-with-email`
- **Description:** Sends an OTP to the user's registered email.

#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com"
}
```

2. **Verify OTP**

- **Endpoint:** `POST http://localhost:9090/auth/verify-email-otp`
- **Description:** Verifies the OTP sent to the user's email.

#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com",
  "otp": "2314"
}
```

---

### 5. **User Login (with Mobile Number)**

To log in using **mobile number**, follow these steps:

1. **Send OTP to Mobile Number**

- **Endpoint:** `POST http://localhost:9090/auth/login-with-mobile`
- **Description:** Sends an OTP to the user's registered mobile number.

#### **Request Body Example:**
```json
{
  "mobileNumber": "7827843470"
}
```

2. **Verify OTP**

- **Endpoint:** `POST http://localhost:9090/auth/verify-otp`
- **Description:** Verifies the OTP sent to the user's mobile number.

#### **Request Body Example:**
```json
{
  "mobileNumber": "7827843470",
  "otp": "8181"
}
```

---

### 6. **Password Reset**

To reset a forgotten password, the user will receive an OTP via email, which must be verified to allow the password reset.

1. **Request Password Reset**

- **Endpoint:** `POST http://localhost:9090/auth/request-password-reset`
- **Description:** Sends a password reset OTP to the user's registered email.

#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com"
}
```

2. **Reset Password**

- **Endpoint:** `POST http://localhost:9090/auth/reset-password`
- **Description:** Resets the user's password by verifying the OTP sent to their email.

#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com",
  "otp": "8573",
  "newPassword": "Kundan*&^$@!!@#32123"
}
```

---

### 7. **Username Reset**

To reset a forgotten username, the user will receive an OTP via email, which must be verified to allow the username reset.

1. **Request Username Reset**

- **Endpoint:** `POST http://localhost:9090/auth/request-username-reset`
- **Description:** Sends a username reset OTP to the user's registered email.

#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com"
}
```

2. **Reset Username**

- **Endpoint:** `POST http://localhost:9090/auth/reset-username`
- **Description:** Resets the user's username by verifying the OTP sent to their email.

#### **Request Body Example:**
```json
{
  "email": "kundangetcode@gmail.com",
  "otp": "8573",
  "newusername": "kundansingh"
}
```

---

### 8. **Categories**

- **Endpoint:** `GET http://localhost:9090/api/categories`
- **Description:** Retrieves a list of available categories in the system.

#### **Response Example:**
```json
[
  {
    "id": 1,
    "name": "Technology"
  },
  {
    "id": 2,
    "name": "Finance"
  },
  {
    "id": 3,
    "name": "Marketing"
  }
]
```
