FROM php:7.4-apache

#installing composer
RUN curl -o /tmp/composer-setup.php https://getcomposer.org/installer \
&& php /tmp/composer-setup.php --no-ansi --install-dir=/usr/local/bin --filename=composer --snapshot

#install php dependecies to laravel
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        libonig-dev \
        graphviz \
        libbz2-dev \
    && apt-get install -y libpq-dev libzip-dev --no-install-recommends zip unzip git\
    && docker-php-ext-install bz2 mysqli pdo_mysql bcmath 
#activate mod_rewrite
RUN a2enmod rewrite
