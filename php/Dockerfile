FROM php:8.2-fpm

# Declaring environments
ARG GIT_REPOSITORY

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    libpq-dev \
    libsodium-dev \
    zip \
    cron \
    unzip

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
 RUN docker-php-ext-install opcache pdo pdo_mysql pdo_pgsql pgsql mbstring exif pcntl gd soap sodium

# Copy default php.ini file do etc
 RUN cp /usr/local/etc/php/php.ini-production /usr/local/etc/php/php.ini

# Get latest Composer
 COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Install and enable Redis
 RUN pecl install -o -f redis && rm -rf /tmp/pear && docker-php-ext-enable redis

# Set working directory
WORKDIR /home

USER root

# Configure permission and access
RUN chmod -R 755 /var/www
RUN chown -R www-data:www-data /var/www