# Use an official PHP runtime as a parent image
FROM php:8.2.3-fpm AS builder

# Set the working directory to /app
WORKDIR /app
COPY src/ .
# Install any necessary packages

RUN apt-get update \
    && apt-get -y install --no-install-recommends apt-utils locales git unzip curl libzip-dev libicu-dev libonig-dev vim libpq-dev libpng-dev \
    && apt-get clean \
    && docker-php-ext-install intl bcmath pdo pdo_mysql pdo_pgsql mbstring zip exif pcntl opcache gd

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Dependency if any need
#RUN composer install -d ./app
RUN composer install --no-interaction --optimize-autoloader --no-dev
