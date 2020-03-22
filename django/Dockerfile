FROM python:3-alpine as base

ENV PYTHONUNBUFFERED 1

RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev jpeg-dev zlib-dev libxml2-dev libxslt-dev

ADD . /framework
WORKDIR /framework

RUN pip install -r requirements.txt

RUN pip install --upgrade pip gunicorn

# I could also put this in docker-compose.yaml, as `command:`
# CMD ["gunicorn", "--bind", "0.0.0.0:8000", "--log-level", "warning", "--reload", "framework.wsgi:application"]
