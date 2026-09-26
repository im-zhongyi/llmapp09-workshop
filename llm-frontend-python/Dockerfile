FROM python:3.12-slim

RUN apt-get update && apt-get upgrade -y && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY app.py config.py ./
COPY static ./static
COPY templates ./templates

RUN useradd --create-home --uid 10001 appuser
USER appuser

EXPOSE 5000

CMD ["python", "app.py"]
