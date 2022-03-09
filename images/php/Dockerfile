FROM php:5.6-fpm-stretch

RUN apt update && \
    apt install -y procps telnet mariadb-client p7zip-full wget less \
    libpng-dev libjpeg-dev libfreetype6-dev && \
    apt clean 
    
RUN docker-php-ext-configure gd --with-jpeg-dir && \
    docker-php-ext-install mysql gd

WORKDIR /app
