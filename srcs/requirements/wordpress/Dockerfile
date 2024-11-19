FROM alpine:3.19

# Create user nginx and add to primary and secondary group nginx (create if it doesn't exist)
RUN addgroup -S nginx && \
	adduser -S -G nginx -g nginx nginx

RUN apk update && \
	apk add --no-cache \
	php83 \
	php83-fpm \
	php83-cgi \
	php83-phar \
	php83-json \
	php83-mysqli \
	php83-curl \
	php83-iconv \
	curl \
	wget \
	composer \
	bash \
	mariadb-client

# Listening port
EXPOSE 9000

# Create and copy paths and confs to cont
RUN mkdir -p /run/php/ /var/www/html/wordpress/

COPY conf/www.conf /etc/php83/php-fpm.d/www.conf

COPY ./tools/script.sh /
RUN chmod +x script.sh

ENTRYPOINT ["sh", "/script.sh"]