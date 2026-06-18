# E-Commerce Platform

A full-stack Django-based e-commerce application featuring restaurant browsing, product catalogs, shopping cart management, checkout, and integrated delivery and payment systems. Includes role-based admin dashboards for staff, customers, and delivery personnel.

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Requirements](#requirements)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [API & Configuration](#api--configuration)
- [Troubleshooting](#troubleshooting)
- [License](#license)

---

## ✨ Features

- **Restaurant Management**: Browse restaurants and view detailed information
- **Product Catalog**: Browse menu items with filtering and search
- **Shopping Cart**: Add/remove items, manage quantities, and view cart summary
- **Checkout System**: Streamlined multi-step checkout process
- **Payment Integration**: Basic payment gateway integration
- **Delivery System**: Order tracking and delivery management
- **Authentication**: Secure login with phone verification
- **Role-Based Dashboards**:
  - **Customer Dashboard**: View orders, track deliveries, manage profile
  - **Delivery Dashboard**: Manage assigned deliveries and routes
  - **Admin Dashboard**: Manage restaurants, items, users, and orders
- **Image Management**: Upload and store product and restaurant images
- **Admin Panel**: Django admin interface at `/admin/`

---

## 🛠 Tech Stack

| Component | Technology |
|-----------|-----------|
| **Backend** | Python 3.10+, Django 5.2.x |
| **API** | Django REST Framework (DRF) |
| **Authentication** | SimpleJWT (JSON Web Tokens) |
| **Database** | SQLite (Development) |
| **Image Processing** | Pillow |
| **Geolocation** | Shapely, NumPy |
| **Frontend** | HTML5, CSS3, JavaScript |

---

## 📦 Requirements

- **Python**: 3.10 or higher
- **pip**: Package manager (included with Python)
- **SQLite**: Bundled with Python (no additional setup needed)

All Python dependencies are specified in `requirements.txt` and will be installed automatically.

---

## 🚀 Installation

### Windows (PowerShell)

```powershell
# 1. Navigate to project directory
cd path\to\E-commerce-

# 2. Create and activate virtual environment (skip if venv/ exists)
python -m venv venv
.\venv\Scripts\Activate.ps1

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run database migrations
python manage.py migrate

# 5. Create superuser account (for admin access)
python manage.py createsuperuser

# 6. (Optional) Load demo data
python manage.py seed_demo

# 7. Start development server
python manage.py runserver
```

**Access the application:**
- Application: `http://127.0.0.1:8000/`
- Admin Panel: `http://127.0.0.1:8000/admin/`

---

## 📂 Project Structure

```
E-commerce-/
├── manage.py                 # Django management script
├── requirements.txt          # Python dependencies
├── db.sqlite3               # SQLite database (local development)
├── testproject/             # Django project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── main/                    # Primary Django app
│   ├── models.py           # Database models
│   ├── views.py            # View logic
│   ├── urls.py             # URL routing
│   ├── serializers.py      # DRF serializers
│   └── management/         # Custom management commands
├── templates/              # HTML templates
│   ├── auth/              # Authentication pages
│   ├── restaurant/        # Restaurant listing & details
│   ├── cart/              # Shopping cart
│   ├── checkout/          # Checkout process
│   ├── customer/          # Customer dashboard
│   ├── delivery/          # Delivery dashboard
│   └── admin/             # Admin dashboard
├── static/                 # Static files (CSS, JS, images)
├── media/                  # User-uploaded files (restaurant/product images)
└── venv/                   # Virtual environment (local only)
```

---

## 📝 Usage

### Common Django Commands

```powershell
# Run unit tests
python manage.py test

# Create a new app
python manage.py startapp myapp

# Database migrations
python manage.py makemigrations
python manage.py migrate

# Collect static files (for production)
python manage.py collectstatic

# Create admin superuser
python manage.py createsuperuser

# Load demo/seed data
python manage.py seed_demo
```

---

## 🔧 API & Configuration

### Environment Variables (Optional)

Configure these environment variables in a `.env` file or system environment:

```env
DEBUG=True                              # Set to False for production
SECRET_KEY=your-secret-key-here         # Strong secret for production
ALLOWED_HOSTS=127.0.0.1,localhost       # Allowed host addresses
DATABASE_URL=sqlite:///db.sqlite3       # Database connection string
```

**Default Configuration**: The project is pre-configured for local development with SQLite and works out-of-the-box.

### Settings Module

The default Django settings module is `testproject.settings`. Adjust configuration based on your deployment environment.

---

## 📦 Data & Media

- **User Uploads**: Stored in the `media/` directory
- **Static Assets**: Located in `static/` (CSS, JavaScript, placeholder images)
- **Demo Data**: Load with `python manage.py seed_demo`

---

## 🐛 Troubleshooting

### Virtualenv Activation Issues (Windows)

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\venv\Scripts\Activate.ps1
```

### Database Locked Error

- Ensure no other processes are accessing `db.sqlite3`
- Stop the development server and retry

### Pillow Installation Issues

- Ensure Python 3.10+ is installed
- Use the virtual environment for installation
- Prebuilt wheels in `requirements.txt` should install automatically

### Shapely/NumPy Slow Installation

- Prebuilt wheels are configured in `requirements.txt`
- If compilation occurs, upgrade pip:
  ```powershell
  python -m pip install --upgrade pip
  ```
- Retry installation

### Migrations Not Applied

```powershell
python manage.py makemigrations
python manage.py migrate
```

---

## 📄 License

This project is for educational and demonstration purposes. Include a LICENSE file if you plan to distribute or open-source this project.

---

## 🤝 Contributing

Contributions are welcome! Please ensure code follows Django best practices and includes appropriate tests.

---

## 📞 Support

For issues or questions, please open an issue on the GitHub repository.
