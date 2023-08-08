FROM php:8.2-fpm

#system dependencies
RUN apt-get update && apt-get install -y \
    git \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip


#php extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

#get Composer: composer is needed to install dependencies
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www
