FROM php:8-apache

# Install mysqli / pdo_mysql
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Enable Apache mod_rewrite (optional)
RUN a2enmod rewrite

WORKDIR /var/www/html