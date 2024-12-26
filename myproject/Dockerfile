FROM python:3.10-slim
WORKDIR /app
RUN pip install --upgrade pip
RUN apt-get update && apt-get install -y \
    libsqlite3-dev \
    gcc \
    && apt-get clean
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt --index-url https://pypi.org/simple
COPY . /app
EXPOSE 8000
CMD [ "python", "manage.py", "runserver", "0.0.0.0:8000"]