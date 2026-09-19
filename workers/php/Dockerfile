FROM php:8.3-cli-alpine@sha256:c8480c242f2145f7b7df3f2adb743a46aa7d9da0b1cbe533def3afc0509a0c31

RUN apk add --no-cache postgresql-dev \
 && docker-php-ext-install pdo pdo_pgsql

WORKDIR /app
COPY worker.php ./

EXPOSE 5002
CMD ["php", "-S", "0.0.0.0:5002", "worker.php"]
