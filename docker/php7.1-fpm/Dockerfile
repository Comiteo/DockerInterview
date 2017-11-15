# USE ARG ?
FROM php:7.1-fpm

RUN apt-get update && apt-get install -y git unzip zlib1g-dev libicu-dev g++ libpng-dev libxml2-dev

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install PHP extensions
RUN apt-get install -y libmcrypt-dev
RUN docker-php-ext-install pdo_mysql intl opcache mcrypt zip bcmath soap
RUN pecl install -o -f redis && docker-php-ext-enable redis
