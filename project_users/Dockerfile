FROM python:3.6-alpine

WORKDIR /app

RUN apk --update add && \
    apk add postgresql-dev gcc python3-dev musl-dev && \
    rm -rf /var/cache/apk/*

COPY requirements.txt .
RUN pip install --upgrade --no-cache-dir pip && \
    pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

RUN addgroup -S appgroup && adduser -S app -G appgroup
USER app

ENV FLASK_APP=src/app.py

CMD python setup.py && flask run --host=0.0.0.0 --port 8000