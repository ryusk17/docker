# Dockerfile 例

# docker hub のimageを指定
# FROM php:8.1-apache
FROM node:18.10.0-alpine3.16
# FROM node:18.10


USER node

WORKDIR /usr/src/app

# RUN npm init @shopify/hydrogen

# RUN apt-get update && \
#     apt-get install -y --no-install-recommends apt-utils vim zip unzip zlib1g git libpng-dev libzip-dev && \
#     docker-php-ext-install -j$(nproc) mysqli pdo_mysql zip gd && \
#     apt-get clean && rm -rf /var/lib/apt/lists/* && \
#     a2enmod rewrite

# COPY --from=composer:2.4.0 /usr/bin/composer /usr/bin/composer

# run composer install
# ENV COMPOSER_ALLOW_SUPERUSER=1 \
#     COMPOSER_NO_INTERACTION=1

# COPY ./docker/php/php.ini /usr/local/etc/php/php.ini
# COPY ./docker/apache/httpd.conf /etc/apache2/sites-available/000-default.conf

# RUN echo pwd: `pwd` && echo ls: `ls -l`

# environment
# ARG BUILD_ENV

# TODO: composer.json作成後
# RUN if [ "${BUILD_ENV}" = "production" ]; \
#     then \
#         composer install --no-dev --no-scripts --optimize-autoloader; \
#     else \
#         composer install; \
#     fi

# ソースコードディレクトリパス(laravel)
# WORKDIR /var/www/html/
