# EtharaAi Backend

Production-ready FastAPI backend for the Inventory & Order Management System.

## Tech Stack

- Python 3.12
- FastAPI
- SQLAlchemy
- PostgreSQL
- Docker

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/products` | Create product |
| GET | `/products` | List products |
| GET | `/products/{id}` | Get product |
| PUT | `/products/{id}` | Update product |
| DELETE | `/products/{id}` | Delete product |
| POST | `/customers` | Create customer |
| GET | `/customers` | List customers |
| GET | `/customers/{id}` | Get customer |
| DELETE | `/customers/{id}` | Delete customer |
| POST | `/orders` | Create order |
| GET | `/orders` | List orders |
| GET | `/orders/{id}` | Get order |
| DELETE | `/orders/{id}` | Cancel order |
| GET | `/dashboard/summary` | Dashboard stats |
| GET | `/health` | Health check |
| GET | `/docs` | Swagger UI |

## Run with Docker

```bash
docker build -t etharaai-backend .
docker run -p 8000:8000 \
  -e DATABASE_URL=postgresql://user:pass@host:5432/dbname \
  -e CORS_ORIGINS=http://localhost:3000 \
  etharaai-backend
```

## Run Locally

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
uvicorn app.main:app --reload --port 8000
```

## Environment Variables

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `CORS_ORIGINS` | Comma-separated allowed frontend URLs |
| `LOW_STOCK_THRESHOLD` | Low stock alert threshold (default: 10) |

## Docker Hub

```
docker pull asitsingh18/inventory-backend:latest
```
