FROM php:5.6-apache-jessie

COPY apache2.conf /etc/apache2/apache2.conf

RUN apt-get update && apt-get install -y \
    libzip-dev \
    libpng-dev \
    zlib1g-dev \
    libpcre3-dev \
    libxml2-dev \
    libicu-dev \
    libxslt-dev \
    libssl-dev 

RUN docker-php-ext-install -j$(nproc) gd mbstring mysqli pdo pdo_mysql zip opcache soap intl xmlrpc
RUN mkdir /var/www/moodledata && chmod 777 -R /var/www/moodledata && chown -R www-data:www-data /var/www/moodledata

VOLUME /var/www/moodledata

EXPOSE 80 443
