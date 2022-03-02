FROM php:5.6-fpm-stretch

RUN apt update && \
    apt install -y procps telnet mariadb-client p7zip-full wget && \
    apt clean 
    
RUN docker-php-ext-install mysql 

WORKDIR /app
