FROM php:8.4-fpm

# Installeer systeem-dependencies en PHP-extensies voor MySQL
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Haal Composer binnen in de container
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

# Start de ingebouwde Laravel server
CMD composer install && php artisan serve --host=0.0.0.0 --port=8000
