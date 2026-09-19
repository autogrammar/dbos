FROM python:3.12-slim@sha256:2c941e860699f878900b0edc2403613c234d4b32eda3cc9fa7036991a2a63c4a
WORKDIR /app

COPY vfs-ftp/requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r /app/requirements.txt

# Shared storage library
COPY libs/platform_storage /app/platform_storage

COPY vfs-ftp/app.py /app/app.py

ENV PYTHONPATH=/app
EXPOSE 2121 30000-30100

CMD ["python", "-u", "/app/app.py"]
