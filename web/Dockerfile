# FROM php:8.1-apache
FROM php:7.4-apache
# FROM php:7.4-fpm
# FROM php:7.4-alpine
# FROM php:8.1-alpine

LABEL maintainer="1@php-cat.com"

# Добавим свой php.ini, можем в нем определять свои значения конфига
ADD php.ini php.ini /usr/local/etc/php/conf.d/40-custom.ini

# RUN apt-get update && \
#      apt-get install -y \
#          libzip-dev \
    # docker-php-ext-install \
RUN docker-php-ext-install \

    #  добавка для работы phpmy admin
    pdo_mysql mysqli \ 
    #    && docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip \
    # && iconv mbstring mysqli pdo_mysql \

    && a2enmod \
    rewrite

# RUN apt-get update

# RUN apt install zip unzip php-zip

# штуки zip для работы композера
RUN apt-get update \
     && apt-get install -y libzip-dev \
     && docker-php-ext-install zip

# RUN apt-get update && apt-get install -y \
#     libmcrypt-dev \
#     && docker-php-ext-install -j$(nproc) mcrypt

# Install composer
# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install composer
# RUN curl -sS https://getcomposer.org/installer | php -- \
#         --filename=composer \
#         --install-dir=/usr/local/bin && \
#         echo "alias composer='composer'" >> /root/.bashrc && \
#         composer

# RUN composer install --prefer-source --no-interaction

# USER www-data

# # RUN cd /var/www/html
# RUN cd html
# RUN curl -sS https://getcomposer.org/installer -o composer-setup.php
# RUN php composer-setup.php
# RUN php composer-setup.php
# RUN rm composer-setup.php
# RUN php composer.phar install