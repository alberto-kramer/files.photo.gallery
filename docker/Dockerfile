#FROM frolvlad/alpine-php
FROM alpine:3.14

RUN apk add --no-cache php7
RUN apk add --no-cache php-json

COPY ./ /www/
ENTRYPOINT ["php", "-S", "0.0.0.0:8080", "-t", "/www"]
