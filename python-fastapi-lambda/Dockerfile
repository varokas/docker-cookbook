FROM python:3.10

WORKDIR /app

RUN pip install poetry
COPY pyproject.toml poetry.lock /app/
RUN poetry export --without-hashes --format=requirements.txt > requirements.txt
RUN pip install -r requirements.txt

COPY *.py /app/

CMD ["uvicorn", "--host", "0.0.0.0", "main:app"]