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
cd church_management
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

Visit `http://127.0.0.1:8000/` in your browser.

## License

This project is licensed under the MIT License.
