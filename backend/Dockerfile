FROM php:7.4-fpm-alpine
 
RUN apk update --no-cache \
&& apk add \
icu-dev \
oniguruma-dev \
tzdata \
php-xml
 
RUN docker-php-ext-install intl
RUN docker-php-ext-install pcntl
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mbstring
 
RUN rm -rf /var/cache/apk/*
 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

#WORKDIRrrr .
COPY composer.json composer.lock ./
RUN composer install --no-scripts --no-autoloader

RUN composer install --no-scripts --no-autoloader

CMD ["php-fpm"]
