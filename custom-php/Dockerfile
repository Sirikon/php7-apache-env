FROM php:7.2-apache
RUN a2enmod rewrite
RUN apt-get update && apt-get install -y zlib1g-dev libicu-dev g++ && \
    docker-php-ext-install intl && \
    docker-php-ext-enable intl

ENV APACHE_DOCUMENT_ROOT /var/www/html/public

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
