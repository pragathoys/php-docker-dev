FROM php:8-apache

# Install zip
RUN apt-get update && apt-get install -y \
        libzip-dev \
        zip \
    && docker-php-ext-install zip
# Install mysqli / pdo_mysql
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Copy Composer from original image
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Copy the installer script directly from its official image
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

# Install the extension seamlessly
RUN install-php-extensions ldap

# Enable Apache mod_rewrite (optional)
RUN a2enmod rewrite

WORKDIR /var/www/html
