FROM php:7.4-fpm

RUN rm /etc/apt/preferences.d/no-debian-php

RUN apt-get update && apt-get install -y zip
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
