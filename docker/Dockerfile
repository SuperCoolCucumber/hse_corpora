FROM python:3.10.8-slim-buster

WORKDIR /code

COPY ../code/requirements.txt /code/requirements.txt

RUN \
    apt-get update \
    && apt-get -y install libpq-dev gcc \
    && pip install --no-cache-dir --upgrade -r /code/requirements.txt

COPY ../code/app /code/app

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8080"]