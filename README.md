# Expense Tracker API

A simple FastAPI + MongoDB expense tracker.

## File Structure

```
expense-simple/
├── app/
│   ├── main.py       ← FastAPI app
│   ├── database.py   ← MongoDB connection
│   ├── models.py     ← Pydantic schemas
│   └── routes.py     ← All API endpoints
├── tests/
│   └── test_expenses.py
├── .github/workflows/ci-cd.yml
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── pytest.ini
└── sample.csv
```

## Run with Docker (easiest)

```bash
docker compose up --build
```

API → http://localhost:8000/docs

## Run Locally

```bash
pip install -r requirements.txt
uvicorn app.main:app --reload
```

## Run Tests

```bash
pytest
```

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | / | Health check |
| POST | /expenses | Add expense |
| GET | /expenses | View all expenses |
| GET | /expenses/{id} | View one expense |
| PUT | /expenses/{id} | Update expense |
| DELETE | /expenses/{id} | Delete expense |
| POST | /expenses/upload-csv | Upload CSV |

## CSV Format

```
title,amount,category,description
Lunch,150,food,Office lunch
Metro,500,transport,
```
