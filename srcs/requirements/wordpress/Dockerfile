FROM debian:bullseye

RUN apt-get update && apt-get install -y \
    wget \
    curl \
    bash \
    php \
    php-cgi \
    php-mysql \
    php-fpm \
    php-pdo \
    php-gd \
    php-cli \
    php-mbstring \
    redis \
    php-redis \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /run/php /var/www/html

EXPOSE 9000