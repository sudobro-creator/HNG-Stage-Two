FROM python:3.11

RUN pip install poetry

WORKDIR /app

COPY pyproject.toml poetry.lock ./

RUN poetry install --no-root

COPY . .

ENV PYTHONPATH=/app

CMD poetry run bash ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000
