# 📡 API Documentation

## Base URL
```
http://localhost:5000/api
```

## Authentication Endpoints

### 1. Register User
**POST** `/auth/register`

إنشاء حساب مستخدم جديد وإرسال رمز التحقق عبر البريد الإلكتروني.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "SecurePass123",
  "name": "أحمد محمد",
  "phone": "0555123456",
  "preferredLanguage": "ar"
}
```

**Response (201):**
```json
{
  "message": "تم إنشاء الحساب بنجاح. يرجى التحقق من بريدك الإلكتروني",
  "userId": 1,
  "emailSent": true
}
```

---

### 2. Verify Email
**POST** `/auth/verify-email`

التحقق من البريد الإلكتروني باستخدام رمز OTP.

**Request Body:**
```json
{
  "email": "user@example.com",
  "code": "123456"
}
```

**Response (200):**
```json
{
  "message": "تم التحقق من البريد الإلكتروني بنجاح"
}
```

---

### 3. Resend Verification Code
**POST** `/auth/resend-verification`

إعادة إرسال رمز التحقق.

**Request Body:**
```json
{
  "email": "user@example.com"
}
```

**Response (200):**
```json
{
  "message": "تم إرسال رمز التحقق مرة أخرى",
  "emailSent": true
}
```

---

### 4. Login
**POST** `/auth/login`

تسجيل الدخول للمستخدمين المؤكدين.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "SecurePass123"
}
```

**Response (200):**
```json
{
  "message": "تم تسجيل الدخول بنجاح",
  "user": {
    "id": 1,
    "email": "user@example.com",
    "name": "أحمد محمد",
    "role": "user",
    "preferredLanguage": "ar"
  }
}
```

---

### 5. Logout
**POST** `/auth/logout`

تسجيل الخروج.

**Response (200):**
```json
{
  "message": "تم تسجيل الخروج بنجاح"
}
```

---

### 6. Get Current User
**GET** `/auth/me`

الحصول على معلومات المستخدم الحالي.

**Headers:**
```
Cookie: connect.sid=<session-id>
```

**Response (200):**
```json
{
  "user": {
    "id": 1,
    "email": "user@example.com",
    "name": "أحمد محمد",
    "role": "user",
    "preferredLanguage": "ar"
  }
}
```

---

## Delivery Endpoints (قريباً)

### Create Delivery
**POST** `/deliveries`

### Get All Deliveries
**GET** `/deliveries`

### Get Delivery by ID
**GET** `/deliveries/:id`

### Update Delivery Status
**PATCH** `/deliveries/:id/status`

### Delete Delivery
**DELETE** `/deliveries/:id`

---

## Error Responses

### 400 Bad Request
```json
{
  "message": "البريد الإلكتروني غير صالح"
}
```

### 401 Unauthorized
```json
{
  "message": "غير مصرح"
}
```

### 404 Not Found
```json
{
  "message": "المستخدم غير موجود"
}
```

### 500 Internal Server Error
```json
{
  "message": "حدث خطأ في الخادم"
}
```

---

## Status Codes

| Code | Description |
|------|-------------|
| 200  | Success |
| 201  | Created |
| 400  | Bad Request |
| 401  | Unauthorized |
| 404  | Not Found |
| 500  | Internal Server Error |

---

## Authentication

يستخدم التطبيق **Session-based Authentication** مع **Passport.js**.

بعد تسجيل الدخول، يتم حفظ الجلسة في cookie:
```
connect.sid=<session-id>
```

يجب إرسال هذا الـ cookie مع كل طلب يتطلب المصادقة.

---

## Rate Limiting (قريباً)

سيتم إضافة حد للطلبات لمنع الإساءة:
- 100 طلب / 15 دقيقة للمستخدم الواحد
