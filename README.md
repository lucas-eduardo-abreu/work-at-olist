# work-at-olist — Library Management API

REST API for a library catalog: bulk author import from CSV and full book management.
Built as part of the Olist technical assessment.

## Stack

- Python 3.12 · Django 5 · Django REST Framework
- PostgreSQL
- Docker + docker-compose

## Features

- Bulk import of authors from CSV (handles 1M+ rows efficiently)
- Paginated author list with optional name search
- Full CRUD for books with multi-author support
- Filter books by name, edition, publication year, or author

## Running locally

```bash
cp .env.example .env
docker-compose up -d
python manage.py migrate
python manage.py import_authors authors.csv
```

API at `http://localhost:8000/api/`. Browsable DRF interface available in development.

## Tests

```bash
pytest --cov=. --cov-report=term-missing
```

## Deploy

Configured for Render via `render.yaml`. Set `DATABASE_URL`, `SECRET_KEY`, and
`ALLOWED_HOSTS` in the dashboard environment.

## API reference

See [API.md](API.md) for full endpoint documentation.
