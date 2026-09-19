FROM python:3.12-slim@sha256:2c941e860699f878900b0edc2403613c234d4b32eda3cc9fa7036991a2a63c4a
WORKDIR /app

COPY vfs-imap/requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r /app/requirements.txt

COPY libs/platform_storage /app/platform_storage
COPY vfs-imap/app.py /app/app.py

ENV PYTHONPATH=/app
EXPOSE 1143

CMD ["python", "-u", "/app/app.py"]
