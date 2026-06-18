# Two Brain

## Description

A RESTful API developed to manage notes, thoughts, and ideas, following a single-tenant model, where each user has access only to their own notes.

This project was designed with a focus on organization, security, and best practices, and was created for personal use.

---

## 🚀 Stack

- **FastAPI** — modern and high-performance web framework
- **SQLAlchemy 2.0** — ORM for database modeling and access
- **PostgreSQL** — relational database
- **pwdlib[argon]** — secure password hashing (Argon2)
- **Alembic** — database migration management

---

## 🗂 Project Structure

The project follows a simple and well-defined structure:

- **Database/**
  Contains everything related to the database: models, sessions, engine, and configurations.

- **routes/**
  Defines all API routes (endpoints), separated by context.

- **security/**
  Responsible for application security, including:
    - Token generation and validation
    - Password hashing and verification

---

## ▶️ Running the project

### 1️⃣ Prerequisites

- **Python 3.10+**
- **PostgreSQL** running
- **uv** installed (dependency manager)

---

### 2️⃣ Cloning the repository

```bash
git clone <repository-url>
cd two-brain
```

---

### 3️⃣ Environment setup

Create a `.env` file based on `.env.example`:

```bash
cp .env.example .env
```

Example environment variables:

```env
DATABASE_URL=postgresql+psycopg://user:password@localhost:5432/twobrain
SECRET_KEY=super-secret-key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=60
```

⚠️ Adjust the values according to your local environment.

---

### 4️⃣ Installing dependencies

Project dependencies are installed using **uv**:

```bash
uv sync
```

---

### 5️⃣ Alembic migrations

The project uses **Alembic** for database versioning.

Create the database tables:

```bash
alembic upgrade head
```

Create a new migration:

```bash
alembic revision --autogenerate -m "migration description"
```

---

### 6️⃣ Running the application

To start the API:

```bash
uv run serv
```

The application will be available at:

```
http://localhost:8000
```

Automatic documentation (Swagger):

```
http://localhost:8000/docs
```

---

### 7️⃣ Development environment (optional)

To install development dependencies:

```bash
uv sync --dev
```

Includes tools such as **pytest** and **ruff**.

---

## ⚙️ In Development

- [ ] Test expansion
- [ ] Complete endpoint documentation
- [ ] Frontend
