# https://hub.docker.com/_/php/

FROM php:fpm-alpine

MAINTAINER Yaroslav Solokha <yaroslav.solokha@gmail.com>

# Install intl
RUN apk add --update --no-cache --repository http://dl-3.alpinelinux.org/alpine/edge/main icu icu-libs icu-dev
RUN docker-php-ext-install intl

# Install Opcache
RUN docker-php-ext-install opcache

# Add php.ini
ADD php.ini /usr/local/etc/php/

# Symfony Installer
RUN mkdir -p /usr/local/bin
RUN curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /app