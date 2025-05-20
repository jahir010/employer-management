# Employer Management

This is a RESTful API for managing employers, built with Django and Django REST Framework.

## Prerequisites

* Python 3.11 or later
* pip (Python package manager)
* Virtualenv (optional but recommended)

## Getting Started

Follow these steps to run the project locally on your machine.

### 1. Clone the Repository

```bash
git clone https://github.com/jahir010/employer-management.git
cd employer-management
```

### 2. Create and Activate a Virtual Environment

It's best practice to isolate dependencies per project.

```bash
# Create a virtual environment named .venv
python3 -m venv .venv

# Activate the virtual environment:
# On Linux/macOS
source .venv/bin/activate

# On Windows (PowerShell)
.\.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. **Configure the Database**

By default, the project uses SQLite. If a different database (e.g., PostgreSQL or MySQL) is configured, update the DATABASES setting in settings.py with your database credentials.

### 5. Apply Migrations

```bash
python manage.py migrate
```

### 6. Create a Superuser (Admin)

```bash
python manage.py createsuperuser
```

Follow the prompts to set your email and password.

### 7. Run the Development Server

```bash
python manage.py runserver
```

By default, the server runs at `http://127.0.0.1:8000/`.

## API Endpoints

* **Authentication**

  * `POST /api/auth/signup/` – Register a new user
  * `POST /api/auth/login/`  – Obtain access and refresh tokens
  * `POST /api/auth/token/refresh/` – Revoke refresh token
  * option /api/auth/logout - Logout user 
  * `GET  /api/auth/profile/` – Get current user profile 

* **Employee Management** 

  * `GET  /api/employers/` - List all Employers for the logged-in user
  * `POST /api/employers/` - Create an Employer
  * `GET  /api/employers/<id>/` - Retrieve a specific Employer
  * `PUT  /api/employers/<id>/`- Update a specific Employe
  * `DELETE /api/employers/<id>/` - Delete a specific Employer
