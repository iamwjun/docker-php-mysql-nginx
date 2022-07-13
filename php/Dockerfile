FROM php:5.6.40-fpm
RUN apt-get update && apt-get install -y \
        libicu-dev \
        libmcrypt-dev \
        default-mysql-client libmagickwand-dev --no-install-recommends \
    && docker-php-ext-install \
        intl \
        opcache \
    && pecl install imagick \
    && docker-php-ext-enable \
        intl \
        opcache \
        imagick \
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install bcmath

RUN apt-get install -y unzip zlib1g-dev libpng-dev
RUN docker-php-ext-install zip
RUN docker-php-ext-configure gd \
    --with-gd \
    --with-freetype-dir
RUN docker-php-ext-install gd