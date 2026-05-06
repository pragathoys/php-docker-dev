FROM php:8-apache

# Install zip
RUN apt-get update && apt-get install -y \
        libzip-dev \
        zip \
    && docker-php-ext-install zip
# Install mysqli / pdo_mysql
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Enable Apache mod_rewrite (optional)
RUN a2enmod rewrite

WORKDIR /var/www/html
