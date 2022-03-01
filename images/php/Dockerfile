FROM php:5.6-fpm-stretch

RUN apt update && apt install -y procps telnet && \
    apt clean 
    
RUN docker-php-ext-install mysql 
