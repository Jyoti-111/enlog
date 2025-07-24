# enlog
Django REST APIs assignment  
# 🛒 Advanced E-commerce API with JWT, Redis Caching & Realtime Notifications

This project is a fully-featured Django REST API for an e-commerce platform.  
Features include user authentication (JWT), product browsing, ordering, Redis caching, and real-time notifications using Django Channels.

---

## 🔧 Features

- ✅ JWT-based Authentication (Register, Login, Profile)
- 🛍️ Product & Category Management (Admin CRUD)
- 🛒 Cart to Order Flow with Status Tracking
- ⚡ Redis Caching (Product List)
- 📡 Realtime Order Status Notifications (WebSocket)
- 🔍 Filtering & Pagination
- 🧪 DRF Browsable API + Postman Ready

---

## ⚙️ Tech Stack

- **Backend:** Django, Django REST Framework
- **Auth:** JWT (SimpleJWT)
- **DB:** PostgreSQL
- **Cache:** Redis
- **Realtime:** Django Channels + WebSocket

---

## 🚀 Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/Jyoti-111/Ecommerce-api.git
cd Ecommerce-api

### 2. Create Virtual Environment

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

### 3. Install requirements

pip install -r requirements.txt

### 4. Setup PostgreSQL 
      Update your ecommerce/settings.py:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'ecommerce_db',
        'USER': 'your_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

then run
python manage.py makemigrations
python manage.py migrate

### 5. Run Redis
Make sure the Redis server is running 

redis-server

### 6. Run the Server

python manage.py runserver

### 6. Run WebSocket with Channels( for real time)

daphne ecommerce.asgi:application

Test API Endpoints:

### 1.POST /api/auth/register/

### 2.POST /api/auth/login/

### 3.GET /api/products/ (filters & pagination)

### 4.POST /api/orders/ with product IDs and quantities

WebSocket: ws://localhost:8000/ws/orders/<user_id>/


Admin Panel
python manage.py createsuperuser

Visit: http://127.0.0.1:8000/admin/
