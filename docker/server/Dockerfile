FROM php:7.2.1-apache

## Install ssmtp and mailutils on the image
RUN apt-get update && apt-get install -q -y msmtp && rm -rf /var/lib/apt/lists/*

## Enables all the required php and apache modules
RUN docker-php-ext-install pdo pdo_mysql mysqli gettext
RUN a2enmod rewrite headers ssl

## Add development mode in PHP.ini
RUN echo "display_errors = On" >> $PHP_INI_DIR/php.ini
RUN echo "display_startup_errors = On" >> $PHP_INI_DIR/php.ini
