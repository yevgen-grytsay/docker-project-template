FROM php:8.2-fpm

RUN apt-get update && apt-get install -y \
        curl \
        wget \
        git \
        libzip-dev \
        libfreetype-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libmcrypt-dev \
    && docker-php-ext-install -j$(nproc) iconv pdo_mysql zip \
    && docker-php-ext-enable pdo_mysql \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd


RUN pecl install xdebug-3.2.1 \
    && docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini

WORKDIR /var/www

# The main purpose of a CMD is to provide defaults for an executing container. These defaults can include an executable,
# or they can omit the executable, in which case you must specify an ENTRYPOINT instruction as well.
CMD ["php-fpm"]
