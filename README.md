# Task Horizon

**Task Horizon** is a powerful task management system built with Django and PostgreSQL, designed to simplify workflow organization and enhance productivity for individuals and teams. **Task Horizon** streamlines task tracking, boosts collaboration, and keeps projects on schedule with a user-friendly interface and scalable design.

## Key Features:

- **User Management:** Secure authentication with role-based access control.
- **Task Management:** Create, assign, and prioritize tasks with deadlines and tags.
- **Collaboration Tools:** Task comments, file attachments, and real-time updates.
- **Notifications & Reminders:** Timely alerts for task deadlines and updates.
- **Reporting & Analytics:** Generate performance and progress reports.
- **Advanced Search:** Filter tasks by keywords, tags, and status.

## Tech Stack

- **Frontend:** HTML5, CSS3, Bootstrap5, JavaScript
- **Backend:** Python=3.11.4, Django=4.2.5
- **Database:** PostgreSQL (can be hosted on Render for Production)
- **Operating System:** Ubuntu 24.04 LTS (WSL)

## Installation (Running locally)

1. Clone the repository

    ```
    git clone https://github.com/Rishabhmohan13/task-horizon.git 
    ```
1. Install dependencies 

    - Python 3.11
    - pip
    - venv
    - postgresql

    ```
    sudo apt install python3-pip venv postgresql postgresql-contrib
    ```
1. Naviage to the project repository

    ```
    cd task-horizon
    ```
1. Setup and activate a python virtual enviourment. *(optional but recommended)*
    
    ```
    python3 -m venv th
    source th/bin/activate
    ```
1. Install all the required packages from `requirements.txt`

    ```
    pip3 install -r requirements.txt
    ```
1. Login to PostgreSQL

    ```
    sudo -u postgres psql
    ```

1. Create a database

    ```
    CREATE DATABASE task_manager;
    ```
1. Create a Superuser and grant privileges to the user

    ```    
    CREATE USER admin WITH PASSWORD 'root12345';
    GRANT ALL PRIVILEGES ON DATABASE task_manager TO admin;
    ```
1. Exit PostgreSQL
    ```
    \q
    ```
1. Create a file named `.env` in the root of the project & add these details

    ```
    SECRET_KEY=your_secret_key
    DEBUG=False
    DB_ENGINE=django.db.backends.postgresql
    DB_NAME=task_manager
    DB_USER=admin
    DB_PASSWORD=root12345
    DB_HOST=localhost
    DB_PORT=5432
    ```
1. Import Data from db.json

    ```
    python3 manage.py loaddata db.json
    ```

1. Run Server

    ```
    python manage.py runserver
    ```

    - Open the browser and go to http://127.0.0.1:8000/
    - To access the admin panel, go to http://127.0.0.1:8000/admin/
    
    - Login with the following credentials:
        - Username: `admin`
        - Password: `admin`
    
    - Steps to create other ADMIN Accounts

    ```
    python manage.py createsuperuser
    ```
