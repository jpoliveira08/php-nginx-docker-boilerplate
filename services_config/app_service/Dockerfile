FROM php:8.3-fpm-alpine

RUN docker-php-ext-install pdo pdo_mysql

COPY --from=composer:2.8.1 /usr/bin/composer /usr/bin/composer

COPY ./src/composer.* ./

RUN composer install --prefer-dist --no-dev --no-scripts --no-progress --no-interaction

COPY ./src .

RUN composer dump-autoload --optimize