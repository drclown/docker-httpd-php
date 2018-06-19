FROM php:7.2-fpm
RUN apt-get update && apt-get install -y zlib1g-dev \
&& pecl install redis-4.0.1 \
&& pecl install xdebug-2.6.0 \
&& docker-php-ext-enable redis xdebug \
&& docker-php-ext-install pdo_mysql \
&& docker-php-ext-install zip

RUN useradd -r -u 1001 php_user -s /bin/false
USER php_user
