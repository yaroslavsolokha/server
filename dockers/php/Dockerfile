# https://hub.docker.com/_/php/

FROM php:fpm-alpine

MAINTAINER Yaroslav Solokha <yaroslav.solokha@gmail.com>

RUN apk add --update --no-cache --repository http://dl-3.alpinelinux.org/alpine/edge/main icu icu-libs icu-dev libpng-dev libmcrypt-dev libxslt-dev freetype-dev libjpeg-turbo-dev g++ make autoconf

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install intl opcache mysqli pdo_mysql xsl zip gd

RUN pecl install redis xdebug
RUN docker-php-ext-enable redis xdebug

# Symfony Installer
RUN mkdir -p /usr/local/bin
RUN curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install NodeJS, NPM
RUN apk update && apk add nodejs

# Install Bower
RUN npm install -g bower

# Install git
RUN apk update && apk add git

# Add php.ini
ADD php.ini /usr/local/etc/php/

WORKDIR /app/projects