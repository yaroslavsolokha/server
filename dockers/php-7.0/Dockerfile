# https://hub.docker.com/_/php/

FROM php:7.0-fpm-alpine

MAINTAINER Yaroslav Solokha <yaroslav.solokha@gmail.com>

RUN apk add --update --no-cache --repository http://dl-3.alpinelinux.org/alpine/edge/main icu icu-libs icu-dev libpng-dev libmcrypt-dev libxslt-dev freetype-dev libjpeg-turbo-dev g++ make autoconf

RUN docker-php-ext-install intl opcache mysqli pdo_mysql mcrypt xsl zip

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install gd

# Add php.ini
ADD php.ini /usr/local/etc/php/

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /app/projects