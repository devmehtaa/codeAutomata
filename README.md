# codeAutomata
block-chain based certificate verification system

# 🔐 Django Authentication API (Knox + DRF)

This API provides secure authentication endpoints using Django REST Framework (DRF) and Token Authentication via **Knox**.

---

## 📌 Base URL

http://127.0.0.1:8000/api/auth/


---

## 🧾 Endpoints

### 1. 🔐 Register a New User

**URL**: `/signup/`  
**Method**: `POST`  
**Authentication**: ❌ Not required  

**Request Body**:
```json
{
  "username": "your_username",
  "email": "your_email@example.com",
  "password": "your_secure_password"
}

**Success Response**

```json
{
  "user": {
    "id": 1,
    "username": "your_username",
    "email": "your_email@example.com"
  },
  "token": "your_knox_token_here"
}

2. 🔓 Login
URL: /login/
Method: POST
Authentication: ❌ Not required

Request Body:

json
Copy
Edit
{
  "username": "your_username",
  "password": "your_secure_password"
}
Success Response:

json
Copy
Edit
{
  "user": {
    "id": 1,
    "username": "your_username",
    "email": "your_email@example.com"
  },
  "token": "your_knox_token_here"
}
3. 🧑‍💻 Get Authenticated User Info
URL: /user/
Method: GET
Authentication: ✅ Token Required

Headers:

makefile
Copy
Edit
Authorization: Token your_knox_token_here
Success Response:

json
Copy
Edit
{
  "id": 1,
  "username": "your_username",
  "email": "your_email@example.com"
}
4. 🚪 Logout
URL: /logout/
Method: POST
Authentication: ✅ Token Required

Headers:

makefile
Copy
Edit
Authorization: Token your_knox_token_here
Success Response:

json
Copy
Edit
{
  "detail": "Successfully logged out."
}
🛠 Setup Instructions
Install dependencies:

bash
Copy
Edit
pip install django djangorestframework django-rest-knox
Add to INSTALLED_APPS in settings.py:

python
Copy
Edit
INSTALLED_APPS = [
    ...
    'rest_framework',
    'knox',
]
Configure REST_FRAMEWORK in settings.py:

python
Copy
Edit
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'knox.auth.TokenAuthentication',
    ]
}
Migrate database:

bash
Copy
Edit
python manage.py makemigrations
python manage.py migrate
Start development server:

bash
Copy
Edit
python manage.py runserver

