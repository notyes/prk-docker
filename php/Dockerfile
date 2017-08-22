FROM php:5-apache
RUN apt-get update && apt install -y libmemcached-dev zlib1g-dev libfreetype6-dev libjpeg62-turbo-dev libpng12-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN a2enmod rewrite
RUN docker-php-ext-install gd mysql mysqli pdo_mysql
RUN pecl install memcache redis
RUN printf "\n" | pecl install memcached-2.2.0
RUN docker-php-ext-enable memcache memcached redis
ADD php.ini /usr/local/etc/php
