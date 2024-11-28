FROM alpine:3.19.4

# Create user nginx and add to primary and secondary group nginx (create if it doesn't exist)
RUN addgroup -S nginx && \
	adduser -S -G nginx -g nginx nginx

RUN apk update && apk add --no-cache \
	php81 \
	php81-phar \
	php81-curl \
	php81-fpm \
	php81-mysqli \
	php81-mbstring \
	php81-json \
	php81-session \
	php81-gd \
	php81-iconv \
	php81-xml \
	php81-simplexml \
	php81-zip \
	php81-tokenizer \
	php81-dom \
	mariadb-client

# Listening port
EXPOSE 9000

# Create a symlink for `php`
RUN ln -s /usr/bin/php81 /usr/bin/php

# Create and copy paths and confs to cont
RUN mkdir -p /run/php/ /var/www/html/wordpress/

COPY conf/www.conf /etc/php81/php-fpm.d/www.conf

COPY ./tools/script.sh /
RUN chmod +x script.sh

ENTRYPOINT ["sh", "/script.sh"]