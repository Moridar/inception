FROM debian:buster

RUN apt-get update && apt-get install -y nginx openssl

COPY conf/nginx.conf /etc/nginx/nginx.conf

COPY tools/certs /etc/nginx/certs

EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]
