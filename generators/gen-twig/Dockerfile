FROM php:8.3-cli-alpine@sha256:c8480c242f2145f7b7df3f2adb743a46aa7d9da0b1cbe533def3afc0509a0c31

# pdo_pgsql for Postgres access
RUN apk add --no-cache postgresql-dev git unzip \
 && docker-php-ext-install pdo pdo_pgsql

# Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /app
COPY composer.json ./
RUN composer install --no-dev --no-interaction --optimize-autoloader

COPY index.php ./

EXPOSE 6002
CMD ["php", "-S", "0.0.0.0:6002", "index.php"]
