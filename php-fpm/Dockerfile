FROM php:8.1-fpm

RUN apt-get update \
    && apt-get install -y libpq-dev git libzip-dev zip unzip \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN docker-php-ext-configure zip

RUN docker-php-ext-configure pgsql \
    && docker-php-ext-install pdo pdo_pgsql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
