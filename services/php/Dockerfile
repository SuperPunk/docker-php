FROM php:7-fpm

RUN apt-get update \
    && apt-get install -y sendmail libpng-dev libfreetype6-dev libjpeg62-turbo-dev

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
        && docker-php-ext-install gd mbstring mysqli pdo_mysql

RUN pecl install redis \
    && docker-php-ext-enable redis

# RUN pecl install xdebug \
#	&& docker-php-ext-enable xdebug \
#	&& echo "xdebug.remote_enable=1" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
#   && echo "xdebug.remote_autostart=1" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
#   && echo "xdebug.remote_host=docker.for.mac.localhost" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \