# FastAPI Blog

A simple blog application built with FastAPI, SQLAlchemy, and Jinja2 templates. Exposes both a web UI and a REST API.

## Features

- Create and browse blog posts via a web interface
- Full REST API for users and posts
- SQLite database via SQLAlchemy ORM
- Profile picture support

## Project Structure

```
.
├── main.py          # App entry point, routes
├── models.py        # SQLAlchemy models (User, Post)
├── schemas.py       # Pydantic schemas for validation
├── database.py      # DB engine and session setup
├── templates/       # Jinja2 HTML templates
├── static/          # CSS, JS, icons
└── media/           # Uploaded profile pictures
```

## Requirements

- Python 3.13+
- FastAPI
- SQLAlchemy
- Pydantic / pydantic[email]
- Jinja2
- uvicorn

Install dependencies (using a virtual environment):

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install "fastapi[standard]"
pip install sqlalchemy
```

## Running the App

```bash
python -m fastapi dev main.py
```

The app will be available at `http://127.0.0.1:8000`.

Interactive API docs: `http://127.0.0.1:8000/docs`

## API Endpoints

### Users

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/users` | Create a new user |
| `GET` | `/api/users/{user_id}` | Get a user by ID |
| `GET` | `/api/users/{user_id}/posts` | Get all posts by a user |

### Posts

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/posts` | List all posts |
| `POST` | `/api/posts` | Create a new post |
| `GET` | `/api/posts/{post_id}` | Get a post by ID |
| `PUT` | `/api/posts/{post_id}` | Replace a post (full update) |
| `PATCH` | `/api/posts/{post_id}` | Update a post (partial update) |

## Web Pages

| Route | Description |
|-------|-------------|
| `/` or `/posts` | Home page — all posts |
| `/posts/{post_id}` | Single post view |
| `/users/{user_id}/posts` | All posts by a specific user |
