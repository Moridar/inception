FROM debian:buster

RUN apt-get update && apt-get install -y php-fpm php-mysql wget tar \
    && wget https://wordpress.org/latest.tar.gz \
    && mkdir -p /var/www/html \
    && tar -xzf latest.tar.gz -C /var/www/html \
    && rm latest.tar.gz

RUN mkdir -p /run/php

COPY conf/php.ini /usr/local/etc/php/

EXPOSE 9000

CMD ["php-fpm7.3", "-F"]