FROM python:3.12 AS base

WORKDIR /app

RUN apt-get update
RUN python -m pip install --upgrade pip
RUN pip install poetry

COPY ../../pyproject.toml /app
COPY ../../lecture_2 /app/lecture_2

RUN poetry install

EXPOSE 8000

CMD ["poetry", "run", "uvicorn", "lecture_2.hw.shop_api.main:app", "--port", "8000", "--host", "0.0.0.0"]