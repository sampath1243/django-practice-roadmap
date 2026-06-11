# Challenge 01 Notes - Django Project Setup

## Objective

Learn how to:

* Create a Virtual Environment
* Activate Virtual Environment
* Install Django
* Create a Django Project
* Run Django Server
* Apply Migrations

---

# Step 1: Create Virtual Environment

Command:

```bash
python -m venv venv
```

Explanation:

* `python` → Run Python
* `-m` → Run module
* `venv` → Virtual Environment module
* `venv` → Folder name

Created Structure:

```text
venv/
├── Include/
├── Lib/
├── Scripts/
└── pyvenv.cfg
```

Purpose:

A virtual environment creates an isolated Python workspace.

Without virtual environment:

```text
Project A
Project B
Project C
```

all share the same Python packages.

With virtual environment:

```text
Project A → Own packages
Project B → Own packages
Project C → Own packages
```

---

# Step 2: Activate Virtual Environment

Windows:

```bash
venv\Scripts\activate
```

Successful activation shows:

```text
(venv)
```

Example:

```text
(venv) PS C:\Users\Sampath>
```

Meaning:

Commands now use packages installed inside this project only.

---

# Step 3: Install Django

Command:

```bash
pip install django
```

Purpose:

Install Django framework.

Installed Packages:

```text
django
asgiref
sqlparse
tzdata
```

Verify Installation:

```bash
django-admin --version
```

Example:

```text
6.0.6
```

---

# Step 4: Create Django Project

Command:

```bash
django-admin startproject student_project
```

Created Structure:

```text
student_project/
│
├── manage.py
│
└── student_project/
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    ├── asgi.py
    └── wsgi.py
```

Purpose of Files:

## manage.py

Main Django management file.

Used for:

```bash
python manage.py runserver
python manage.py migrate
python manage.py startapp
```

---

## settings.py

Project configuration.

Contains:

* Installed apps
* Database settings
* Security settings
* Static files settings

---

## urls.py

Controls routing.

Example:

```python
path("students/", views.students)
```

Meaning:

When user visits:

```text
/students/
```

Django calls:

```python
views.students
```

---

## wsgi.py

Used when deploying Django applications.

---

## asgi.py

Used for asynchronous features such as:

* WebSockets
* Real-time applications
* Chat applications

---

# Step 5: Common Error

Error:

```text
can't open file manage.py
```

Reason:

Running command from wrong folder.

Wrong:

```text
challenge-01-project-setup
```

Correct:

```text
challenge-01-project-setup
└── student_project
    └── manage.py
```

Move into project folder:

```bash
cd student_project
```

Then run:

```bash
python manage.py runserver
```

---

# Step 6: Run Server

Command:

```bash
python manage.py runserver
```

Output:

```text
Starting development server at
http://127.0.0.1:8000/
```

Open browser:

```text
http://127.0.0.1:8000
```

Expected Screen:

```text
The install worked successfully!
Congratulations!
```

---

# Step 7: Apply Migrations

Command:

```bash
python manage.py migrate
```

Purpose:

Create default Django database tables.

Tables created for:

* Authentication
* Admin Panel
* Sessions
* Permissions

Database File:

```text
db.sqlite3
```

SQLite is Django's default database.

---

# Commands Learned

```bash
python -m venv venv

venv\Scripts\activate

pip install django

django-admin startproject student_project

cd student_project

python manage.py migrate

python manage.py runserver
```

---

# Key Learning

1. Virtual environment isolates project dependencies.
2. Django is installed using pip.
3. `django-admin startproject` creates a project.
4. `manage.py` is Django's command center.
5. Always run Django commands from the folder containing `manage.py`.
6. `migrate` creates database tables.
7. `runserver` starts the development server.

---

# Challenge Status

✅ Virtual Environment Created

✅ Environment Activated

✅ Django Installed

✅ Project Created

✅ Migrations Applied

✅ Server Running Successfully

Challenge 01 Completed Successfully.
