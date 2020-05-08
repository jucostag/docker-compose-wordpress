FROM php:7.4.5-fpm

#vim editor
RUN apt-get update \
    && apt-get install -y vim

# gd extension and dependency libpng
RUN apt-get update -y && apt-get install -y libpng-dev
RUN docker-php-ext-install gd

# intl extension
RUN apt-get install -y zlib1g-dev libicu-dev g++ \
&& docker-php-ext-configure intl \
&& docker-php-ext-install intl

# xmlrpc extension and dependency libxml2
RUN apt install -y libxml2-dev \ 
&& docker-php-ext-install xmlrpc

# soap extension
RUN docker-php-ext-install soap

# zip extension and dependency 
RUN apt-get install -y \
libzip-dev \
zip \
&& docker-php-ext-configure zip --with-libzip \
&& docker-php-ext-install zip

# mysqli extension
RUN docker-php-ext-install mysqli