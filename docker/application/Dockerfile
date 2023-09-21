FROM python:3.11

# set work directory
RUN mkdir /app
WORKDIR /app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV APP_NAME=SHOP
#RUN apk update \
#    && apk add postgresql-dev gcc python3-dev musl-dev
RUN pip install --upgrade pip
COPY ../../requirements.txt .
RUN pip install -r requirements.txt
COPY ./docker/application/entrypoint.sh .
# copy project
COPY ../.. .
ENTRYPOINT ["/app/entrypoint.sh"]
#CMD gunicorn core.wsgi:application -b 0.0.0.0:8000
