# Church Management System

This is a Django-based Church Management System that uses PostgreSQL as its database. Follow the instructions below to set up the project on your local machine.

## Prerequisites

Ensure you have the following installed:

- Python (>=3.10)
- PostgreSQL
- Git

## Installation & Setup

### 1️⃣ Clone the Repository

```sh
git clone <repository-url>
cd churchms
```

### 2️⃣ Set Up a Virtual Environment

```sh
pip install pipenv
pipenv shell
```

### 3️⃣ Install Dependencies

```sh
pipenv install
```

### 4️⃣ Configure Environment Variables

Create a `.env` file in the project root and add:

```
DATABASE_NAME=church_db
DATABASE_USER=your_db_user
DATABASE_PASSWORD=your_db_password
DATABASE_HOST=localhost
DATABASE_PORT=5432
SECRET_KEY=your_secret_key
DEBUG=True
```

### 5️⃣ Configure PostgreSQL Database

- Open PostgreSQL and create a database:

```sql
CREATE DATABASE church_db;
CREATE USER your_db_user WITH PASSWORD 'your_db_password';
ALTER ROLE your_db_user SET client_encoding TO 'utf8';
ALTER ROLE your_db_user SET default_transaction_isolation TO 'read committed';
ALTER ROLE your_db_user SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE church_db TO your_db_user;
```

### 6️⃣ Apply Migrations

````sh
Run the following command in your terminal while inside the project directory:
```sh
python manage.py migrate
````

````

### 7️⃣ Create a Superuser (For Admin Access)
```sh
python manage.py createsuperuser
````

Follow the prompts to set up an admin account.

### 8️⃣ Run the Development Server

```sh
python manage.py runserver
```

## Project Structure

```
churchms/
│
├── manage.py
├── README.md
├── Pipfile.lock
├── .gitignore
├── .env
├── churchms/
│ ├── **init**.py
│ ├── settings.py
│ ├── urls.py
│ ├── wsgi.py
│ ├── asgi.py
│ └── static/
│
├── apps/
│ ├── **init**.py
│ └── ...
│
├── templates/
│ ├── base.html
│ └── ...
│
└── static/
  ├── css/
  ├── js/
  └── images/
```

## Project Structure Overview

The structure is designed to keep the project modular and easy to scale. Here’s a breakdown of the key components:

## 1. manage.py

This is the main entry point for running Django commands like migrations, starting the development server, and more. It is a standard file in Django projects.

## 2. README.md

This file provides an overview of the project and includes setup instructions, dependencies, and other necessary information for developers who want to contribute or run the project.

## 3. Pipfile.lock

Contains a list of Python packages required to run the project. This is used by pipenv to install the dependencies.

## 4. .gitignore

Defines files and directories that Git should ignore. Common examples include virtual environment files, Python bytecode files (.pyc), and other files that don’t need to be tracked in version control.

## 5. .env

    This file contains environment variables such as database credentials, secret keys, and other sensitive information. It is not tracked by Git to keep these details secure.

# Main Project Directory: churchms/

    This is the core of the Django project, which includes configuration files and settings.

## Key Files:

**init**.py: Marks the directory as a Python package.

# settings.py:

    Contains all the settings for the project, like database configurations, installed apps, middleware, etc. This could also be     split into separate files like base.py, dev.py, and prod.py to manage different environments.

## urls.py:

    This is where the URL routing happens. It connects the URLs to the views or apps that will handle requests.

## wsgi.py:

    This is the entry point for the WSGI-compatible web server to serve your project (e.g., when deploying the project).

## asgi.py:

    Similar to wsgi.py but for asynchronous servers, used when the project needs support for WebSockets or other asynchronous tasks.

## static/:

    This directory holds global static files (e.g., images, CSS, JavaScript) that can be used across the entire project. You may choose to manage static files within individual apps, but this is for global use.

## apps/

This is where all the Django applications (or "apps") will live. Each app is a modular unit with its own models, views, controllers, and other components that are focused on a specific feature or service within the system.

Each app contains:

#### migrations/:

Tracks the changes to your models and creates database migrations.

#### models.py:

Defines the data models (tables) for the app.

#### views.py:

Contains the logic for handling requests and returning responses.

#### admin.py:

Configures the app's models to be accessible via the Django Admin interface.

#### apps.py:

Contains configuration for the app, such as its name.

#### tests.py:

Contains tests to ensure the app behaves as expected.

#### urls.py:

Defines the app-specific URL routing.

#### static/:

App-specific static files.

#### templates/:

App-specific templates (HTML files).

#### templates/

This folder contains global templates that are used throughout the project. For example, a base template with header and footer sections that can be extended by app templates.

#### base.html:

This file can define common layout elements (e.g., header, footer, navigation) that can be extended by other templates. Other templates can be added here to be used globally.

## static/

Contains all the global static assets (e.g., images, CSS, JavaScript files). These files will be accessible across the entire application.

### css/:

For global CSS styles.

### js/:

For global JavaScript files.

### images/:

For global image assets.

## Why This Structure?

#### Modular Design:

The structure encourages a modular approach where each app encapsulates a specific feature of the project. This makes it easier to manage and extend the system in the future.

#### Scalability:

As your project grows, you can easily add new apps for different features (e.g., a membership app, a donation app, etc.).

#### Separation of Concerns:

Keeping global files (e.g., templates, static files) separate from app-specific ones ensures that the system remains organized and maintainable.

#### Django Best Practices:

The structure follows Django’s standard best practices, making it easier for new developers to understand and contribute to the project.

Visit `http://127.0.0.1:8000/` in your browser.

## License

This project is licensed under the MIT License.
