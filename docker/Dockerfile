FROM python:3.11-alpine

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

RUN apk add bash
RUN pip install --upgrade pip

COPY requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt

RUN adduser -D apiuser

RUN mkdir /app
COPY --chown=apiuser:apiuser . /app/
WORKDIR /app

USER apiuser

EXPOSE 8000