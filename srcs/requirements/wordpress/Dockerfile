FROM debian:buster

RUN apt-get udpate & apt-get install -y php-fpm php-mysql wget tar \
	&& wget https://wordpress.org/latest.tar.gz \
	&& tar -xzf lastest.tar.gz -C /var/www/html \
	&& rm latest.tar.gz

COPY conf/php.ini /usr/local/etc/php/

EXPOSE 9000

CMD ["php-fpm"]