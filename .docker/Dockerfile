FROM php:7.4-apache
RUN mkdir /srv/app
COPY .docker/vhost.conf /etc/apache2/sites-available/000-default.conf
COPY .docker/php /srv/app/public

WORKDIR /srv/app
RUN apt-get update && apt-get install -y \
    libzip-dev libpng-dev libjpeg-dev zip
RUN apt-get install -y libc-client-dev libkrb5-dev

RUN docker-php-ext-install mysqli pdo pdo_mysql zip gd
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl && docker-php-ext-install imap
COPY suitecrm_source /srv/app
RUN chown -R www-data:www-data /srv/app \
    && a2enmod rewrite