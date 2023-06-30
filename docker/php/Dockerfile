FROM php:8.2-apache
RUN  a2enmod rewrite
RUN apt-get update && \
  apt-get install -y zlib1g-dev libzip-dev unzip && \
  docker-php-ext-install zip  && \
  pecl install xdebug && \
  docker-php-ext-enable xdebug
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer