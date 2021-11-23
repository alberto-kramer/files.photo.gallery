#FROM frolvlad/alpine-php
FROM alpine:3.14

RUN apk add --no-cache php7
RUN apk add --no-cache php-json
RUN apk add --no-cache php7-gd

# Update Php Settings
RUN sed -E -i -e 's/max_execution_time = 30/max_execution_time = 120/' /etc/php7/php.ini \
 && sed -E -i -e 's/memory_limit = 128M/memory_limit = 128M/' /etc/php7/php.ini \
 && sed -E -i -e 's/post_max_size = 8M/post_max_size = 64M/' /etc/php7/php.ini \
 && sed -E -i -e 's/upload_max_filesize = 2M/upload_max_filesize = 64M/' /etc/php7/php.ini

COPY ./ /www/
ENTRYPOINT ["php", "-S", "0.0.0.0:8080", "-t", "/www"]
