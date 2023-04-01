FROM php:8.2.4-fpm

## Install dependencies
RUN apt-get clean \
    && apt-get update \
    && apt-get install -y \        
        libzip-dev \
        git \
        zip \
        unzip \
    && docker-php-ext-install \ 
        mysqli \
        pdo_mysql \
        bcmath \
        zip \
        exif

## INTL extension for PHP
# RUN apt-get install -y \
#         zlib1g-dev libicu-dev g++ \
#     && docker-php-ext-configure intl \
#     && docker-php-ext-install \ 
#         intl

## GD extension for PHP
# RUN apt-get install -y \
#         libpng-dev \
#         libwebp-dev \
#         libjpeg62-turbo-dev \
#         libfreetype6-dev \
#     && docker-php-ext-configure gd --with-webp=/usr/include/webp --with-jpeg=/usr/include --with-freetype=/usr/include/freetype2/ \
#     && docker-php-ext-install \ 
#         gd

## Install Composer
COPY --from=composer /usr/bin/composer /usr/bin/composer 