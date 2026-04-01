FROM python:3.12-slim

WORKDIR /app

RUN apt update -y \
    && apt install -y build-essential libpq-dev \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .

RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir psycopg2-binary && \
    pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5153

CMD ["python", "app.py"]