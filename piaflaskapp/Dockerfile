FROM python:3.9-slim-buster

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

ENV FLASK_APP=app.app
ENV FLASK_DEBUG=1
ENV FLASK_RUN_HOST=0.0.0.0

CMD ["python", "-m", "flask", "run", "--host", "0.0.0.0"]

