# Django Authentication API :

## 1. Sign up:
### URL - http://127.0.0.1:8000/api/auth/signup/
**Request Body**:
```json
{
    "username" : "devv",
    "email" : "dev@gmaill.com",
    "password" : "12345"
}
```
**Success Body**:
```json
{
    "user": {
        "id": 2,
        "username": "devv",
        "email": "dev@gmaill.com"
    },
    "token": "c92256aa64006363f7b69ad8aa199d4328a08034c4e71389a6be0bc7ef96d0ba"
}
```

## 2. Login:
### URL - http://127.0.0.1:8000/api/auth/login/
**Request Body**:
```json
{
    "username" : "devv",
    "password" : "12345"
}
```
**Success Body**:
```json
{
    "user": {
        "id": 2,
        "username": "devv",
        "email": "dev@gmaill.com"
    },
    "token": "c055e462fce73484bccb829338b855b99bb7cf4fedc68bcf5391496b357d27d8"
}
```

## 3. User Info:
### URL - http://127.0.0.1:8000/api/auth/user/
**Request Body**: Header
```json
{
    "Authorization" : "Token c055e462fce73484bccb829338b855b99bb7cf4fedc68bcf5391496b357d27d8",
}
```
**Success Body**:
```json
{
    "id": 2,
    "username": "devv",
    "email": "dev@gmaill.com"
}
```

## 4. Logout:
### URL - http://127.0.0.1:8000/api/auth/logout/
**Request Body**: 
```json
{
    "Authorization" : "Token c055e462fce73484bccb829338b855b99bb7cf4fedc68bcf5391496b357d27d8",
}
```
**Success Body**:
```json
```



