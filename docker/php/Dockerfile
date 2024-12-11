FROM php:8.2-fpm

WORKDIR /var/www/laravel

RUN docker-php-ext-install pdo pdo_mysql

RUN pecl install xdebug-3.2.0 && docker-php-ext-enable xdebug

COPY conf.d/* $PHP_INI_DIR/conf.d/
